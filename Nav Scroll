//Simple Debounce to reduce the amount of resources used on the scroll function
function debounce(func, wait = 20, immediate = true) {
	var timeout;
	return function() {
		var context = this, args = arguments;
		var later = function() {
			timeout = null;
			if (!immediate) func.apply(context, args);
		};
		var callNow = immediate && !timeout;
		clearTimeout(timeout);
		timeout = setTimeout(later, wait);
		if (callNow) func.apply(context, args);
	};
};
//Get the Nav Bar Variation & General Nav Bar Div
const navBar = document.querySelector('.nav-primary');
const generalNav = document.querySelector('.site-header');
const landingPageNav = document.querySelector('.page-template-landing-page');
//Check if the user/page is scrolled at least 1px down the page
var section1 = $('#section1');

function checkDistance(e) {
	if (window.scrollY > 1) {
		//Fade in the secondary Nav
		$(navBar).addClass('nav-secondary');
		$(generalNav).addClass('site-header-shrink');
		$('.site-header.page-template-landing-page').css('paddingBottom', '56px');
	} else {
		//Fadeout the secondary Nav
		$(navBar).removeClass('nav-secondary');
		$(generalNav).removeClass('site-header-shrink');
		$('.site-header.page-template-landing-page').css('paddingBottom', '56px');
	}
}
//When user scrolls down page, run the function..Or on page load if the viewport is at least 1px down the page
window.addEventListener('scroll', debounce(checkDistance));
