#Template for the Reborn CMS

View files for reborn are HTML file. Reborn use parser to parse the your view file (html) to php file.

This is the basic parser of Reborn CMS

**Echo the variable at view**

	{{ $header }}

**Use function at view**

	{{ h($content) }}
	// h() is the helper function of reborn. Same with htmlspecialchars()

	{{ var_dump($content) }}

**Loop (foreach only) the data at view**

	{{ loop($breadcrumbs as $name => $url) }}
		{{ if(! is_null($url)) }}
			<a href="{{ $url }}" >{{ $name }}</a>
		{{ else }}
			<span>{{ $name }}</span>
		{{ endif }}
	{{ endloop }}

**Conditional statement at view**

	{{ if(isset($user['name'])) }}
 		<p> Have the {{ $user.name }} </p>
 	{{ endif }}
 	/*
 	{{ $user.name }} is equal with <?php echo $user['name']; ?>
 	*/

 	// How to use elseif
 	{{ if(condition) }}
 		Condition is equal with if
 	{{ elseif(some) }}
 		Condition is equal with elseif
 	{{ else }}
 		Condition is equal with else

**PHP Comment at the view**

	{# This is PHP Comment single line comment #}

	{##
		This is
		PHP Comment Block
		For the test
	##}

**How to skip the PHP echo**

	{% $a %}
	// Out put is <?php $a; ?>

**How to call another partial file from the layout file or partial file**

	{{ include:nav }}
	// This is call the nav.html file from the partial folder.


