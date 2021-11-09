CKEditor 5 for laravel-admin
======

## Installation

```bash
composer require kitamula/ckeditor
```

Then
```bash
php artisan vendor:publish --tag=kitamula-ckeditor
```

## Configuration

In the `extensions` section of the `config/admin.php` file, add some configuration that belongs to this extension.
```php

    'ckeditor' => [
    		
    		    //Set to false if you want to disable this extension
    		    'enable' => true,
    		
    		    // Editor configuration
    		    'config' => [
    			   "simpleUpload"=>[
    			   	    "uploadUrl"=>'/admin/uploads'
    			   ],
    			    "fontSize" => [
    			    	"options" =>[
    					    9,
    					    11,
    					    13,
    					    'default',
    					    17,
    					    19,
    					    21
    				    ]
    			    ],
    			    "toolbar"=>[
    			    	"items"=>[
    					    'heading',
    					    'fontFamily',
    					    'fontSize',
    					    'fontColor',
    					    'fontBackgroundColor',
    					    'bold',
    					    'italic',
    					    'link',
    					    'bulletedList',
    					    'numberedList',
    					    '|',
    					    'indent',
    					    'outdent',
    					    '|',
    					    'imageUpload',
    					    'blockQuote',
    					    'insertTable',
    					    'mediaEmbed',
    					    'undo',
    					    'redo'
    				    ]
    			    ],
    			    'image'=>[
    			    	'toolbar'=>['imageTextAlternative', '|', 'imageStyle:alignLeft', 'imageStyle:full', 'imageStyle:alignRight'],
    				    'resizeUnit'=>'px',
    				    'styles'=>[
    					    // This option is equal to a situation where no style is applied.
    					    'full',
    					
    					    'side',
    					    // This represents an image aligned to the left.
    					    'alignLeft',
    					    'alignCenter',
    					    // This represents an image aligned to the right.
    					    'alignRight'
    				    ]
    			    ],
    			    
    			    "table" =>[
    			    	'contentToolbar'=>[
    					    'tableColumn',
    					    'tableRow',
    					    'mergeTableCells'
    				    ]
    			    ],
    			    'language'=>'ja',
    		    
    		    ]
    	    ]

```

## Usage

Add the following code to `app/Admin/bootstrap.php`

```php
Encore\Admin\Form::extend('editor', \kitamula\CKEditor\Editor::class);
```