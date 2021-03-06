# Sassee

At runtime Sassee checks if the SASS source file is newer than the parsed CSS file and only runs the parser if that is the case, else it just returns the parsed CSS file. If you specify an output folder that doesn't exists, Sassee will attempt to create it.

**IMPORTANT: Make sure your CSS output folder is writable and your SASS source folder is readable.**

## Tags

###{exp:sassee:file}###

The file tag outputs the URL to the parsed CSS file. If you haven't set a specific syntax to use, it will try to determine it by looking at the source file extension. Else the extension setting is used for syntax.

Either set the _file_ parameter or the _template_ parameter. If both are set the file parameter is used.

    {exp:sassee:file 
      file='site.sass'
      template='stylesheets/site' 
      [syntax='scss'] // sass|scss
      [style='compressed'] // nested|expanded|compact|compressed
      [sass_path='/full/path/to/sass/'] 
      [css_path='/full/path/to/css/'] 
      [css_url='/css'] 
      [output_file='style.css'] 
      [debug='yes']
    }
    
## Parameters

**file**<br />
Source file to load from the folder defined with `sass_path`. Either the `file` or `template` parameter is required.

**template**<br />
Template to load as source. Either the `file` or `template` parameter is required.

**syntax** [optional]<br />
Syntax to use for parsing the source file. If not specified it will determine the syntax based on the source file extension or fall back on the syntax specified in the extension settings. Accepted values: `sass` or `scss`.

**style** [optional]<br />
Style to use for output. Can be `nested`, `expanded`, `compact` or `compressed`. If not specified, it will fall back on the style specified in the extension settings.

**sass_path** [optional]<br />
Override the source folder specified in the extension settings.

**css_path** [optional]<br />
Override the output folder specified in the extension settings.

**css_url** [optional]<br />
Override the output URL specified in the extension settings.

**output_file** [optional]<br />
Set the filename to use for the output file. If not specified it will derive the output filename from the source file.

**debug** [optional]<br />
The debug parameter will turn on debugging info for the SASS parser. This is great if you want to know which lines in your SASS file are used while watching it in your browser. If you are a firefox user, [FireSass](https://github.com/nex3/firesass) is a great tool to aid in this.<br  />
<br />
When you turn on debugging, your CSS isn't cached and the parsing style is set to `expanded` (a requirement for the parser). When you're done with debugging, make sure to remove the file and let Sassee generate a new, fresh copy of your CSS.

## Links

[Support](http://support.baseworks.nl/discussions/sassee)<br />
[Developer site](http://www.baseworks.nl/)<br />
[GitHub repository](https://github.com/AboutWout/sassee.ee2_addon)

## Changelog

**v 1.0 - 07.16.2011**<br />
- Added `debug` parameter

**v 0.9 - 07.11.2011**<br />
- Initial release