# Canvas "Login with Google" button to SAML
Adds a button to the Canvas Login page to log in using SAML

(button simply redirects to /login/saml)

```////////////////////////////////////////////////////
// BEGIN Google Login Button                      //
////////////////////////////////////////////////////
$("div.ic-Login__body").append('<div class="ic-Login__sso">    <ul class="ic-Login__sso-list">        <li class="ic-Login__sso-list__item">          <a href="/login/saml" class="Button Button--primary ic-Login__sso-button--has-text ic-Login__sso-button ic-Login__sso-button--google">              <span class="ic-Login_icon-sso ic-Login_icon-sso--icon-only" role="presentation">  <svg class="ic-icon-svg ic-icon-svg--google" version="1.1" viewBox="0 0 32 32" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" xml:space="preserve"><path d="M29,0H3C1.4,0,0,1.4,0,3v26c0,1.6,1.4,3,3,3h26c1.6,0,3-1.4,3-3V3C32,1.4,30.6,0,29,0z M16.2,28c-6.6,0-12-5.4-12-12	s5.4-12,12-12c3.2,0,5.9,1.2,8,3.1L21,10.3c-0.9-0.9-2.5-1.9-4.8-1.9c-4.1,0-7.4,3.4-7.4,7.6s3.3,7.6,7.4,7.6c4.8,0,6.5-3.4,6.8-5.2	h-6.8v-4.1h11.3c0.1,0.6,0.2,1.2,0.2,2C27.8,23.1,23.2,28,16.2,28L16.2,28z"></path></svg></span>  <span class="ic-Login__sso-button__title ic-Login__sso-button__title--google">    Login with Google  </span>          </a>        </li>    </ul>  </div>');

// Adds the Google login button for mobile
if (typeof jQuery == 'undefined' || typeof jQuery === undefined || typeof jQuery === null) {
	var headTag = document.getElementsByTagName("head")[0];
	var jqTag = document.createElement('script');
	jqTag.type = 'text/javascript';
	jqTag.src = 'https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js';
	headTag.appendChild(jqTag);
	jqTag.onload = myJQueryCode;
} else {
	myJQueryCode();
}

function myJQueryCode() {
	$(document).ready(function() {

		(function() {
			'use strict';
			if (/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent) && $('#login_form')) {
				var googleHTML = document.createElement('center');
				googleHTML.innerHTML = '<center><br><br><a href="/login/saml" class="btn btn-primary btn-large"> <span class="ic-Login_icon-sso ic-Login_icon-sso--icon-only" role="presentation"> <img src="https://lh3.googleusercontent.com/DKoidc0T3T1KvYC2stChcX9zwmjKj1pgmg3hXzGBDQXM8RG_7JjgiuS0CLOh8DUa7as=w300" style="width: 20%;"></span> <span class="ic-Login__sso-button__title ic-Login__sso-button__title--google"><br>Login with <span class="ic-Login__sso-button__title-caps">Google</span> </span> </a></center>';
				document.getElementById('login_form').appendChild(googleHTML);
			}
		})();
	});
}

////////////////////////////////////////////////////
// END Google Login Button                        //
////////////////////////////////////////////////////```
