#Widgets

##Theme Developer

Before using widgets you need to declare widget areas in **info.php** of your theme. if you don't declare your widget areas, Widget Manager will not detect any widget area.

**info.php**

	'widget_areas' => array(
		'sidebar' => 'Sidebar Area',
		'header'  => 'Header Area',
		'footer' => 'Footer Area'
	)
	
**Call Widget Area in theme**
    
    // Eg. {{ widgetArea:sidebar }}
    
    {{ widgetArea:areaName }}
    
##Widget Developer

**If you have sub Widget in your Widget Class please specify your sub widget with 'sub' keyname in properties array like this**
    
    protected $properties = array(
			'name' 			=> 'Blog Module Widget',
			'sub' 			=> array(
				'posts' 	=> array(
					'title' => 'Blog Post',
					'description' => 'Latest Blog Posts which is posted last days',
				),
				'archive' 	=> array(
					'title' =>'Blog Archive',
					'description' => 'Blog by Year and month',
				),
				'category' 	=> array(
					'title' => 'Blog Category',
					'description' => 'Blog Category List',
				),
				'tagCloud'	=> array(
					'title' => 'Blog Tag Cloud',
					'description' => 'Blog Tag Cloud',
				),
			),
			'author' => 'Reborn CMS Development Team'
		);

Please include function name **options** for widget settings. If your widget don't have settings just return empty array.

**if you have sub widgets return array like this**

      public function options() 
	  {
		return array(
			'posts' => array( //function name of your sub widget
				'title' => array( //key for your setting
					'label' 	=> 'Title', //label for your input field
					'type'		=> 'text', //type of your input field
					'info'		=> 'Info text for your input field',
				),
				'limit' 	=> array(
					'label' 	=> 'Number of Posts',
					'type'		=> 'text',
				),
			),
			'category' 	=> array(
				'title' => array(
					'label' 	=> 'Title',
					'type'		=> 'text',
					'info'		=> 'Leave it blank if you don\'t want to show your widget title',
				),
			),
		);
	 }
	 
**If there is not sub widgets**
    
    public function options() 
	  {
		return array(
			'title' => array( 
			    'label' 	=> 'Title', //label for your input field
			    'type'		=> 'text', //type of your input field
			    'info'		=> 'Info text for your input field',
			),
			'limit' 	=> array(
				'label' 	=> 'Number of Posts',
				'type'		=> 'text',
			),
		);
	 }
	 
** Note : Currently only 3 types of input field is avaliable for options

* text
* textarea
* select

**Example array for text field**
    
    return array(
        'title' => array(
            'label'     => 'Title', 
            'type'      => 'text', 
            'info'      => 'Info text for your input field',
        ),
    );

**Example array for textarea field**

    return array(
        'description' => array (
            'label'    => 'Description',
            'type'     => 'textarea',
        ),
    );

**Example array for select field**
    
    return array(
        'show_type' => array(
            'label'    => 'Way to show category',
            'type'     => 'select',
            'options'  => array( //options for your select
                'list' => 'List Style',
                'drop_down' => 'DropDown Style',
            ),  
        ),
    );



