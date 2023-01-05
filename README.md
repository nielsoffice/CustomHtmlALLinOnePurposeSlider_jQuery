# Dynamic HTML Custom Multi-purpose slider with jQuery
Custom Html ALL in One Purpose Slider with jQuery

```JS

   /**
   * Cooked by nielsoffice
   **/
    var slideInterval          = 2000;
    var parentContainerSlider  = jQuery('#slider'); // select parent container
    var parentContainerListTag = jQuery('.slides'); // select slider container
    var childListTags          = '.slides li';      // select slider child
    var childListTagsActive    = '.slides li.active';  // select slider child active
   
    jQuery(() => {

        const performSlides = jQuery.fn.sliderDynamicPost = function() { 

             let childFirst = jQuery( childListTags ).first().show('fast',function() { 
        
             $( this ).addClass('active');  

             if( jQuery( childListTags ).first().hasClass('active') === true ) {

                var childCountList = 1;
                
                setInterval(function() { 

                    let __sliders = jQuery(childListTags).length;
                    let __counts  = childCountList++;               

                    if( jQuery( parentContainerListTag ).find('li').hasClass('active') ) {

                     jQuery(childListTagsActive).hide().removeClass('active');
           
                     if( __counts >= __sliders ) 
                     
                     { childCountList = 0;  __counts = childCountList++; } 
 
                     jQuery(childListTags).eq( __counts ).show().addClass('active');

                   } 
    
                },  slideInterval );
             } 
          }); 
        };

        performSlides();
        
    });

```
