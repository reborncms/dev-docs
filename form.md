#Security Class for RebornCMS

**namespace** - Reborn\Form

Form elements for RebornCMS

##How to use Form Class

###start($action = '', $name = null, $file = false, attrs = array())

Open Form Tag

* **$action** *(string)* Form Action
* **$name** *(string)* Form Name
* **$file** *(boolean)* Send form-data as multipart/form-data [default=false]
* **$attrs** *(array)* Form tag attributes

**Example**

    //<form action="blog/create" name="form_name" method="post" enctype="multipart/form-data">
    Form::start('blog/create', 'form_name', true);


###end()

Close form tag

**Example**

    //</form>
    Form::end();


###fieldsetStart($legend = null, $name = null, attrs = array())

Open fieldset tag

* **$legend** *(string)* Text to show in legend tag
* **$name** *(string)* Fieldset Name
* **$attrs** *(array)* Fieldset tag attributes

**Example**
    
    //<fieldset name="fieldset_name" class="fieldset_class">
    //    <legend>Legend Text</legend>
    Form::fieldsetStart('Legend Text', 'fieldset_name',array('class' => 'fieldset_class'));


###fieldsetEnd()

Close fieldset tag

**Example**

    //</fieldset>
    Form::fieldsetEnd();


###input($name, $value = null, $type = 'text', $attrs = array())

Form Input

* **$name** *(string)* Input name
* **$value** *(string)* Input Value
* **$type** *(string)* Input Type [default='text']
* **$attrs** *(array)* Input tag attributes

**Example**

    //<input type="text" name="input_name" id="input_name" value="RebornCMS" />
    //if you didn't place id attributes, id will set the same as name
    Form::input('input_name','RebornCMS');


###password($name, $value = null, $attrs = array())

Password Input Field

* **$name** *(string)* Input Password name
* **$value** *(string)* Input Password Value
* **$attrs** *(array)* Input tag attributes

**Example**

    //<input type="password" name="field_name" id="field_name" />
    Form::password('field_name');


###hidden($name, $value = null, $attrs = array())

Hidden Input Field

* **$name** *(string)* Hidden Input name
* **$value** *(string)* Hidden Input Value
* **$attrs** *(array)* Input tag attributes

**Example**

    //<input type="hidden" name="field_name" id="field_name" value="reborn" />
    Form::hidden('field_name','reborn');


###file($name, $attrs = array())

File Input Field

* **$name** *(string)* Hidden Input name
* **$attrs** *(array)* Input tag attributes

**Example**

    //<input type="file" name="field_name" id="field_name">
    Form::file('field_name');


###email($name, $value = null, $attrs = array())

Email Input Field

* **$name** *(string)* Email Input name
* **$value** *(string)* Email Input Value
* **$attrs** *(array)* Input tag attributes

**Example**

    //<input type="email" name="field_name" id="field_name">
    Form::email('field_name');


###url($name, $value = null, $attrs = array())

Url Input Field

* **$name** *(string)* Url Input name
* **$value** *(string)* Url Input Value
* **$attrs** *(array)* Input tag attributes

**Example**

    //<input type="url" name="field_name" id="field_name">
    Form::url('field_name');


###tel($name, $value = null, $attrs = array())

Tel Input Field

* **$name** *(string)* Tel Input name
* **$value** *(string)* Tel Input Value
* **$attrs** *(array)* Input tag attributes

**Example**

    //<input type="tel" name="field_name" id="field_name">
    Form::tel('field_name');


###search($name, $value = null, $attrs = array())

Search Input Field

* **$name** *(string)* Search Input name
* **$value** *(string)* Search Input Value
* **$attrs** *(array)* Input tag attributes

**Example**

    //<input type="search" name="field_name" id="field_name">
    Form::search('field_name');


###number($name, $min, $max, $value = null, $step = null)

Html5 Number Field with a spinner control

* **$name** *(string)* Number Input name
* **$min** *(int)* Minimum value
* **$max** *(int)* Maximum value
* **$value** *(int)* Default value
* **$step** *(int)* Specific legal number intervals

**Example**

    //<input type="number" name="field_name" id="field_name" min=0 max=10 />
    Form::number('field_name', 0, 10);


###submit($name, $value, $attrs = array())

Form Submit Button

* **$name** *(string)* Submit button name
* **$value** *(string)* Submit button value
* **$attrs** *(array)* Input tag attributes

**Example**

    //<input type="submit" name="submit_button" value="Submit" id="submit_button">
    Form::submit('submit_button','Submit');


###reset($name, $value, $attrs = array())

Form Reset Button

* **$name** *(string)* Reset button name
* **$value** *(string)* Reset button value
* **$attrs** *(array)* Input tag attributes

**Example**

    //<input type="reset" name="reset_button" value="Reset" id="reset_button">
    Form::search('reset_button','Reset');


###button($name, $text, $type = 'button', $attrs=array())

Form Button

* **$name** *(string)* Button name
* **$text** *(string)* Button Text
* **$type** *(string)* Button Type [default=button]
* **$attrs** *(array)* Input tag attributes

**Example**

    //<button name="button_name" type="button">Button</button>
    Form::button('button_name', 'Button');


###label($text, $for = null)

Form Label

* **$text** *(string)* Label Text
* **$for** *(string)* for which text field

**Example**

    return <label for="field_name">Label</label>
    Form::label('Label', 'field_name');


###radio($name, $value, $attrs = array())

Radio Input

* **$name** *(string)* Radio Input name
* **$value** *(string)* Radio Input Value
* **$attrs** *(array)* Input tag attributes

**Example**

    //<input type="radio" name="gender" id="field_name" value="male">
    Form::radio('gender', 'male');


###radioGroup($name, $val_lab = array(), $checkedVal = null)

Group of Radio Inputs

* **$name** *(string)* Radio Input name
* **$val_lab** *(array)* radio Value and Label
* **$checkedVal** *(string)* Value of Defaut Checked radio

**Example**
    
    /* <label>
        <input type="radio" name="gender" value="male" checked="checked" />
        Male
    </label>
    <label>
        <input type="radio" name="gender" value="female" />
        Female
    </label> */
    Form::radioGroup('gender', array( 
                        'male' => 'Male', 
                        'female' => 'Female'
                        ), male);


###checkbox($name, $value, $attrs = array())

Checkbox

* **$name** *(string)* Checkbox name
* **$value** *(string)* Checkbox Value
* **$attrs** *(array)* Input tag attributes

**Example**

    //<input type="checkbox" name="color" value="red" id="color">
    Form::checkbox('color', 'red');


###ckboxGroup($name, $val_lab = array(), $checkVals = array())

Group of Checkboxes

* **$name** *(string)* Checkbox name
* **$val_lab** *(array)* Checkbox Value and Label
* **$checkedVal** *(array)* Default checked boxes

**Example**

    /* <label for="color[1]">
        <input type="checkbox" name="color[1]" value="red" checked="checked" />
        Red
    </label>
    <label for="color[2]">
        <input type="checkbox" name="color[2]" value="yellow" />
        Yellow
    </label>
    <label for="color[3]">
        <input type="checkbox" name="color[3]" value="green" />
        Green
    </label> */
    Form::ckboxGroup('color', array(
                        'red' => 'Red', 
                        'yellow' => 'Yellow', 
                        'green' => 'Green'), array('red'));


###textarea($name, $value = null, $attrs = array())

Form Textarea

* **$name** *(string)* Textarea name
* **$value** *(string)* Textarea Value
* **$attrs** *(array)* Input tag attributes

**Example**

    //<textarea name="textarea_name">Type your text here</textarea>
    Form::textarea('textarea_name','Type your text here');


###select($name, $options, $multisel = false, $defaultSel = null, attrs = array())

Form Select

* **$name** *(string)* Form Select name
* **$options** *(array)* Select Options
* **$multisel** *(boolean)* Enable if you want multiselect box [default=false]
* **$defaultSel** *(mixed)* Default select value / give with array if default value is more than one
* **$attrs** *(array)* Input tag attributes

**Example**

    /* <select name="color" id="color" multiple="multiple">
        <option value="none">None</option>
        <optgroup label="Light Color">
            <option value="s_blue" selected="selected">Sky Blue</option>
            <option value="l_green">Light Green</option>
        </optgroup>
        <option value="black" selected="selected">Black</option>
        <option value="white">White</option>
    </select> */
    Form::select('color',array(
                    'none' => 'None',
                    'Light Color' => array(
                        's_blue' => 'Sky Blue',
                        'l_green' => 'Light Green'
                        ),
                    'black' => 'Black',
                    'white' => 'White',
                    ), true, array('black','s_blue'));


###CountryList()

CountryList with Select

**Example**

    Form::CountryList();
