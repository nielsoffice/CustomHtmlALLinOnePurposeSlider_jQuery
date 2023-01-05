# CustomHtmlALLinOnePurposeSlider_jQuery
Custom Html ALL in One Purpose Slider with jQuery

```JS

    var slideInterval          = 1000;
    var parentContainerSlider  = jQuery('#slider'); // select parent container
    var parentContainerListTag = jQuery('.slides'); // select slider container
    var childListTags          = '.slides li';      // select slider child
    var childListTagsActive    = '.slides li.active';  // select slider child active
   
    // do run selft function!
    jQuery(() => {

        // create function for basic slider
        const performSlides = jQuery.fn.sliderDynamicPost = function() { 

             // first child should be shown
             let childFirst = jQuery('.slides li').first().show('fast',function() { 
        
             // add active class for layouts which the first child slider
             $( this ).addClass('active');  
            
             // check if the first slide has active class
            if( jQuery('.slides li').first().hasClass('active') === true ) {

                // set default second child 1 since first child which is 0 having already active class
                var childCountList = 1;
                
                // Loop slide with interval 2 seconds!
                setInterval(function() { 

                    // Get slider lenght / dynamic how many slides we have
                    let __sliders = jQuery(childListTags).length;
                    // Once interval run 1 + 1 + 1 soon....!
                    let __counts  = childCountList++;               

                    // check if any of slides having class active
                    if( jQuery('.slides').find('li').hasClass('active') ) {

                     // when you found the slider or child have class then hide and remove class active !
                     jQuery(childListTagsActive).hide().removeClass('active');
                     
                     // Check if childCountList not greather than current child elements
                     // If Child  1 + 1 + 1 soon....! is greather than current number of sliders
                     // Then set array to first child which is 0 array
                     // Then from first which which 0 childCountList + 1 + 1 + 1 soon....!
                     // Then back to 0 over and over again
                     if( __counts >= __sliders ) { childCountList = 0;  __counts = childCountList++; } 

                    // Using that count we select which child slider will be active slides
                    // Show and add class active! 
                    jQuery(childListTags).eq( __counts ).show().addClass('active');

                   } 
    
                }, 2000 );

            } 

          }); 
   
        };

        performSlides();

        // Bonus for Library !
        // to get interval for slide to call again
        // get total of delay from each slides ex. 2 slides each slide having 1000 interval
        // 2000 + 1000 when the slides rich 2000 for 3k it will reload again and do slides!

        // setInterval(performSlides,slides ); 

    });

```
