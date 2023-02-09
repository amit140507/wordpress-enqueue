# wordpress-enqueue
## Reference Code

```
function custom_enqueue_style() {
	// wp_enqueue_script( $handle, $src, $deps, $ver, $in_footer );
	// wp_enqueue_style('enqueue name', path , array(), number/false/null , false inside </head> and true inside </body>);

	// wp_enqueue_style('custom-style', get_stylesheet_directory_uri().'/assets/css/custom.css', array(),null ,false);     //  for no version

	wp_register_style('custom-style', get_template_directory_uri() . '/assets/css/custom.css',array(), '1.0.0', false);
	wp_register_style('font_awesome_css', 'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.2.1/css/all.min.css', array(),'6.2.1',false);

	wp_enqueue_style('custom-style');
	wp_enqueue_style('font_awesome_css');
}
add_action( 'wp_enqueue_scripts', 'custom_enqueue_style' );

function custom_enqueue_script() {

    wp_enqueue_script('jquery');   // Use this if wanna use build in Jquery Version.
	// wp_register_script('jquery3', 'https://code.jquery.com/jquery-3.6.1.js'array(),'3.6.1', true);
	// wp_register_script('jquery-migrate', 'https://code.jquery.com/jquery-migrate-3.4.0.min.js', array(),'3.6.1', true);
	wp_register_script('font_awesome_js', 'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.2.1/js/all.min.js', array(),time(), true);
	 wp_register_script('jquery_validate', 'https://cdnjs.cloudflare.com/ajax/libs/jquery-validate/1.19.5/jquery.validate.min.js', array(), '1.19.5', true );
	wp_register_script('custom-script', get_template_directory_uri() . '/assets/js/custom.js', array(), '1.0.0', true ); 
	// wp_enqueue_script('jquery3');
	// wp_enqueue_script('jquery-migrate');
	 wp_enqueue_script('jquery_validate');
	wp_enqueue_script('font_awesome_js');
	wp_enqueue_script('custom-script');

	// $style_ver = filemtime( get_stylesheet_directory() . '/assets/js/custom.js' );
    // wp_enqueue_script('allyearcooling_custom_js', get_stylesheet_directory_uri().'/assets/js/custom.js', array(), $style_ver);

}
add_action( 'wp_enqueue_scripts', 'custom_enqueue_script' );
```
## Ready to Use Code
```
/* Enqueue Styles and Scripts */

function custom_enqueue_style() {
	
	wp_register_style('custom-style', get_template_directory_uri() . '/assets/css/custom.css',array(), '1.0.0', false);
	wp_register_style('font_awesome_css', 'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.2.1/css/all.min.css', array(),'6.2.1',false);

	wp_enqueue_style('custom-style');
	wp_enqueue_style('font_awesome_css');
}
add_action( 'wp_enqueue_scripts', 'custom_enqueue_style' );

function custom_enqueue_script() {

    wp_enqueue_script('jquery');   // Use this if wanna use build in Jquery Version.

    wp_register_script('font_awesome_js', 'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.2.1/js/all.min.js', array(),time(), true);
    wp_register_script('jquery_validate', 'https://cdnjs.cloudflare.com/ajax/libs/jquery-validate/1.19.5/jquery.validate.min.js', array(), '1.19.5', true );
    wp_register_script('custom-script', get_template_directory_uri() . '/assets/js/custom.js', array(), '1.0.0', true ); 

    wp_enqueue_script('jquery_validate');
    wp_enqueue_script('font_awesome_js');
    wp_enqueue_script('custom-script');

}
add_action( 'wp_enqueue_scripts', 'custom_enqueue_script' );
```
## References

### [wp_register_script](https://developer.wordpress.org/reference/functions/wp_register_script/)

### [wp_enqueue_script](https://developer.wordpress.org/reference/functions/wp_enqueue_script/)

### [get_template_directory_uri()](https://developer.wordpress.org/reference/functions/get_template_directory_uri/)

Retrieves template directory URI for the active theme.

**NOTE: In the event a child theme is being used, this function will return the child’s theme directory URI. Use get_template_directory_uri() to avoid being overridden by a child theme.**

### [get_stylesheet_directory_uri()](https://developer.wordpress.org/reference/functions/get_stylesheet_directory_uri/)

Retrieves stylesheet directory URI for the active theme.
