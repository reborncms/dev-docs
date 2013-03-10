#Pagination Class for RebornCMS

**namespace** - Reborn\Util

Create pagination for many items

**Pagination Options**

* **total_items** Total items to paginate [required]
* **url** Url to paginate [required]
* **items_per_page** Items to show on one page [default = 5]
* **current** Current Page number [default = 1]
* **uri_segment** Uri Segment of pagination number [required]
* **show_links** Number of links to show in pagination [default = 10]
* **show_adj** Number of Adjacent links to show [default = 2]
* **numbers_pagi** Enable number pagination [default = true]

**Pagination Template Options**

	array(
		'start_container' => '<div class="pagination">',
		'end_container' => '</div>',
		'start_page_link' => '<li>',
		'end_page_link' => '</li>',
		'active_class' => 'active',
		'pre_link_class' => 'pagi_pre',
		'next_link_class' => 'pagi_next',
		'pre_link_text' => '&laquo; Prev',
		'next_link_text' => 'Next &raquo;',
		'separator'	=> '...',
		'separator_class' => 'separator'
	);

##Example Usage

**Set Options**
	
	//Example with Eloquent ORM
	$options = array(
		'total_items' 		=> Post::all()->count(),
		'url'		  		=> 'blog',
		'items_per_page' 	=> 5,
		'template'			=> array(
			'start_page_link' => '<span>',
			'end_page_link'	  => '</span>',
		),
	);

**Create Pagination**

	$pagination = \Pagination::create($options);

**Get Post from Database**

	$posts = Post::skip(\Pagination::offset())->take(\Pagination::limit())->get();




