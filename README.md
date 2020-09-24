# cheatSheet for Contao

**tl_page.php - _add_icon_to_tl_page_operations**

Adds a new icon in the tl_page operations.\
This script adds a Button to jump directly into an article.\
Tested in Contao 4.7

\
**config.php - _rsce_Gallery_order and rscr_whatever_config.php**

To change the image order in rock solid custom elements.

\
**config.php - _deactivate_Node_picker_in_Article_Page_and_Files**

Deactivate the nodepicker (Backend Breadcrumb-Menü) in Contao.

\
**tl_content_or_some_other.php - Add text-information-block to cte's**
```php
'palettes' => array
(
   'default' => 'fieldInformation'
)
# new Field
'fieldInformation' => array
(
    'input_field_callback'    => array('tl_content_or_some_other', 'fieldInformationMethod'),
),


public function fieldInformationMethod(\DataContainer $dc, $label)
{
  $icon = $this->generateImage('show.gif', $GLOBALS['TL_LANG']['tl_calendar_events']['helpmode'][0], ' style="vertical-align:-4px"');
  return '<div style="margin-left: 15px;margin-right: 15px;line-height:1.3rem;">
  <h3><label style="color:#8ab858">'.$icon. ' Information</label></h3>
  Some Text ....
  </div>';
}

  ```
