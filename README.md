# hide-product-category-js-css
Hides a category on the product category page using vanilla JavasScript and CSS

<script type="text/javascript">
// Plain JS

// Make sure the page has finished loading the DOM
document.addEventListener('DOMContentLoaded', function () {
// Get user's current URL from browser
let url      = window.location.pathname; 
console.log(url);
// Is this the Product category listing we want to hide a category from? 
if(url == "index.html") {
// Inline a style sheet to the HTML document 
// since we can't rely on html elements being loaded because of lazy loading 
    let style = document.createElement('style');   
    // This would be unique to your page.  I used nth-last-child since the PCP we 
    // needed to hide was always on the bottom of the page. 
    // You could get more fancy and find the the listing however you want but this was the easiest
    let css = '#categories-list li:nth-last-child(1){' +
        'display: none;}';       
    style.innerHTML = css;
    //What element of the list (li) do we want to hide?
    let lastElement = 1;
    // Let the browser know we want to add the the css to the first found script 
    let ref = document.querySelector('script');
    // Insert in the body
    ref.parentNode.insertBefore(style, ref);
  } 
});
</script>
