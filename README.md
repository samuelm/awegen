# awegen

awegen is a code generator for Yii framework.  
awegen borrows goodies from giix and gtc.  

### What It Does?

1. Generates textarea for `text` db type
2. Genearates textarea with markitp editor for `longtext` db type
3. Generates checkbox for `boolean` db types
4. Uses JToggleColumn for 'boolean' types in Admin/CGridView
5. Generates fields with Datepicker for date db type
5. Generates fields with Datetimepicker for time, datetime and timestamp db type
6. Allows easy addition of access control templates in the generator  
( Users can add templates into `AweCrud/templates/default/auth` folder and they will be listed in the CRUD generator)
7. Guesses e-mail fields by field names and adds e-mail validation for forms and mailto links for views
8. Guesses image fields by field names and tries to display the image in views
9. Guesses url fields by field names and adds url validation for forms and creates links for views
10. Guesses password fields by field names, generates password fields for them in forms and hides them from non-admin users in views
11. Guesses createtime and updatetime fields and adds proper timestamp behaviour to them
12. Uses EActiveRecordRelationBehavior behaviour to handle all kinds of relations
13. Creates pulldown menu for one-to-many and one-to-one relations
14. Creates checkboxes for fields with many-to-many relations
15. Keeps generated code in abstract base model so that regeneration doesn't overwrite user changes
16. Guesses identification column for models and uses them in headings and breadcrumbs  
(Looks for fields - name, title, slug, any field  with `name` in its name, first non-numeric field, primarykey in pripority order)
17. Handles parent-child relationship of items among same model
(Allows an item to be parent/child of any other items from the same table but not itself)

### Installation

Download from <https://github.com/awecms/awegen>

Extract the awegen folder from the archive to extensions directory of your application.

Add the path of awegen to generatorPaths section in the module configuration in `config/main.php`

        'modules' => array(
                'gii' => array(
                    'class' => 'system.gii.GiiModule',
                    'password' => 'password',
                    'generatorPaths' => array(
                        'ext.awegen',
                    ),
                ),
                ...
            ),

Add the components required to your imports section

        'import' => array(
            ...
            'application.extensions.awegen.components.*',
            ),


### Usage

Browse to /gii, login and select AweModel Generator to create Model and then AweCrud to generate Controller and Views.