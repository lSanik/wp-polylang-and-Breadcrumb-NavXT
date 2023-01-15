# wp-polylang-and-Breadcrumb-NavXT
Solution to fix home page for polylang and Breadcrumb NavXT in WordPress (WP)

If you have issue with your home page url, when you change secondary language, but your url showing for primary language.

Just add this for your function.php in your theme folder 

```
add_action('bcn_after_fill', function($bcn_breadcrumb_trail){
	foreach ($bcn_breadcrumb_trail->breadcrumbs as $index => $value){
		if(in_array('home',$bcn_breadcrumb_trail->breadcrumbs[$index]->get_types())){
			$bcn_breadcrumb_trail->breadcrumbs[$index]->set_url( pll_home_url());
		}
	}
});
```
