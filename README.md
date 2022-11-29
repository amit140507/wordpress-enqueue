# wordpress-enqueue
wordpress enqueue

```
function custom_enqueue_style() {
	// https://developer.wordpress.org/reference/functions/wp_enqueue_script/



	 // wp_enqueue_style('enqueue name', path , array(), number/false/null , false inside </head> and true inside </body>);


	// wp_register_style(	'custom-style',	get_template_directory_uri() . '/assets/css/custom.css',array(), '1.0.0', true);
	// wp_enqueue_style( 'custom-style');
	//OR 

	// wp_enqueue_style( 'custom-style', get_template_directory_uri() . '/assets/css/custom.css', array(), '1.0.0', true);   //    ?ver=1.0.0
	// wp_enqueue_style('custom-style', get_stylesheet_directory_uri().'/assets/css/custom.css', array(), date("h:i:s"), false);
	wp_enqueue_style('custom-style', get_template_directory_uri().'/assets/css/custom.css', array(), false);     // ?ver=6.1
	// wp_enqueue_style('custom-style', get_template_directory_uri().'/assets/css/custom.css', array(), false ,false);     // ?ver=6.1  media=''
	// wp_enqueue_style('custom-style', get_stylesheet_directory_uri().'/assets/css/custom.css', array(),null ,false);     //  media=''
	// wp_enqueue_style('custom-style', get_stylesheet_directory_uri().'/assets/css/custom.css', null,null ,false);     //  media=''


	// CDN

	wp_enqueue_style('font_awesome_css', 'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.2.1/css/all.min.css', array(), false);
}


function custom_enqueue_script() {
	wp_enqueue_script( 'custom-script', get_template_directory_uri() . '/assets/js/custom.js', array(), '1.0.0', true ); 


	//CDN
	wp_enqueue_script('font_awesome_js', 'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.2.1/js/all.min.js', array(), true);
	wp_enqueue_script('jquery');

	// if you want your own version of Jquery then
	//wp_deregister_script('jquery');
	//wp_enqueue_script('jquery', 'https://code.jquery.com/jquery-3.3.1.js', array(), null, true);

	//$style_ver = filemtime( get_stylesheet_directory() . '/assets/js/custom.js' );
    //wp_enqueue_script('allyearcooling_custom_js', get_stylesheet_directory_uri().'/assets/js/custom.js', array(), $style_ver);
}

add_action( 'wp_enqueue_scripts', 'custom_enqueue_style' );
add_action( 'wp_enqueue_scripts', 'custom_enqueue_script' );
```
