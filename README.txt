Theme design samples for TheBigFork.com

Folder explanation:

All three folders are essentially the same.

 * minimal_theme  = contains the fewest possible files needed to achieve the theme's design
 * sample_theme   = contains more *.html.erb files which can be customized but are not required
 * sample_website = contains a rendered sample using the theme

How To Design a Theme for TheBigFork

Themes consist of several components. Nearly all of the files and folders are optional. TheBigFork provides defaults where needed. It is possible to create a new theme with nothing more than a CSS file. 

Folders
When creating a new theme, it is best to start with our minimal theme or sample theme—which provide the following folder structure:

/sample_theme
  /images
  /javascripts
  /stylesheets
  /views
    /layouts
    /websites
    /website_pages
    /shared

Rename “sample_theme” with the name of your theme. The remaining folders should keep their names. Any images, javascript files, or CSS files are to be placed in their corresponding folders. Sample javascript and CSS files are provided. Keep the filenames the same unless you plan heavy customization in the HTML layout files.

CSS
The sample CSS file (website.css) contains inline comments describing each element in the pages. Please refer to it for more information. Take special note of the path to image files. Your exact path depends on the folder name for your theme:

/themes/THEME_FOLDER_NAME/images/image_name.png

(where THEME_FOLDER_NAME is the name you gave the folder as described in the “Folders” section of this document.)

Layout Files
The “layouts” folder contains two HTML files. These are actually ERB templates—which is a common template language used in Ruby on Rails applications. TheBigFork fills in all the content where <%=  %> tags appear. Keep these in your custom layout files, but you may move them around as needed to suit your design.

There are two sample layout files. The file “website_home.html.erb” corresponds to the homepage. The other, “websites.html.erb,” corresponds to all sub-pages.

Other “Views”
The remaining folders within the “views” folder control how the individual content pages appear.

Homepage Dissection
It is strongly recommended to view the HTML sources provided to get a feel for the elements that are expected on the homepage:
•	Page head – most of the page header can remain the same.  Advanced designers can use this section to load 3rd party hosted javascript libraries or Google web fonts, for example. Javascript which is loaded by default: JQuery, Twitter widget, Google Analytics, Google Maps (when needed)
•	Div “id=home_container” – this div only appears on the homepage and can be styled differently than the other pages
•	Header – an HTML5 header container
•	Div “id=logo” – appears on all pages and is filled with a user-uploaded logo (or an “h1” text if no logo is provided)
•	<%= main_navigation %> renders an HTML5 “nav” container with a simple unordered list (ul) which you can style as needed.
•	<%= website_slideshow() %> renders a slideshow within a div “id=slideshow_container” which you can style as needed. See the sample_website for a rendered version.
•	Div “id=home_content_container” appears only on the homepage and can be styled differently than the other pages.
•	Div “id=side_bar” renders the user’s twitter feed (if provided). The style of the twitter feed can be customized by providing a file in  views/shared/_website_twitter_feed.html.erb
•	<%= yield %> fills in the user’s page content
•	Div “id=ad_support” inserts a google adsense ad if the user’s account is un-paid. This must appear somewhere on the page along with its contents.
•	<%= render “shared/website_footer” %> does exactly what it says. The footer contains facebook/twitter links, site navigation, theme credits, and links to TheBigFork (if the account is unpaid).
Content Page Dissection
It is strongly recommended to view the HTML sources provided to get a feel for the elements that are expected on the content pages:
•	Header, logo, navigation, footer are all the same as the home page.
•	Div “id=page_container” lets you style the page content differently than the home page
•	Div “id=page_content” is also different from the homepage and simply contains the individual page content.
•	Div “id=side_bar” is unused on content pages for now.

Other Details
In addition to the files in your theme, you will need to provide the following values when uploading a theme:

•	Theme name (must be unique)
•	The folder name which contains your theme files (must be unique)
•	Description (one or two sentences—appears on our customers’ theme selection page)
•	Preview image (auto-scaled to 640x480 and 128x176 to appear on our customer’s theme section page)
•	Slide size (example: 960x400. If your homepage has a slideshow, provide the dimensions of the slides which the theme user should upload)
•	Designer name and/or user ID on TheBigFork.com





