# DBWiki

**DBWiki** is a free template for hugo static website generator. This template ressembles a wiki website for internal use. I use it for bundling my config files and installation notes for my computers/mobile stuff.

1. [Content Tree](#content-tree)
2. [Custom CSS](#custom-css)
3. [Google WebFonts](#google-webfonts)
4. [Fonts](#fonts)
5. [Config.toml Parameters](#configtoml-parameters)
6. [Frontmatter Parameters](#frontmatter-parameters)

## Content Tree

You can use folders and subfolders for your content, below you find my content organization.

        content
            _index.md
            bits
                _index.md
            config
                _index.md
                linux
                    _index.md
                macos
                    _index.md
                windows
                    _index.md
            installation
                _index.md
                linux
                    _index.md
                macos
                    _index.md
                windows
                    _index.md

Make sure to add '_index.md' to every folder and subfolder. You can create your own content tree, but above you get an idea of what's possible.

## Custom CSS

The **template** comes with a basic CSS, which can be extended or even replaced by yuor own custom CSS.
To add your custom css file place it in the folder named 

        static/css

in your hugo website.

Then in your config.toml file add a parameter to include your css files, they can be multiple files.

        [params]
            stylesheets = ["css/your_custom_css_file.css"]

If everything is set right this must be enough to load your own custom css files into the website.

## Google WebFonts

You can add **Google WebFonts** to your website, just copy the URL into a parameter and your set to go.

example

        [params]
            google_webfonts = ["https://fonts.googleapis.com/css2?family=Lato:wght@300&display=swap"]


## Fonts

You can even add your own fonts in the folder

        static/fonts/your_font.ttf

If done you can access them in your own website's css by using the example below.

        @font-face {
        	font-family: "nasalization";
	        src: url("../fonts/nasalization-rg.ttf");
        }

## config.toml Parameters

There are several parameters that must be implemented in your 'config.toml' file of your website.

You can use one 

        [params]
            all your parameters
            go here

Every parameter must be on their own line.
Here is an overview of the parameters which must be set, if any is not set the website will complain about it visually.

        [params]
            read_more_text = "Lees meer..."
            logo_path = ""
            logo_text = "DBHQ Wiki"
            prefix_static_files = "/dbhq-wiki"
            sidebar_tags = 1
            menu_tags = 0
            pagination_number = 10
            pagination_older_text = "ouder"
            pagination_newer_text = "nieuwer"
            stylesheets = ["css/main.css"]
            google_webfonts = ["https://fonts.googleapis.com/css2?family=Lato:wght@300&display=swap"]

Below you find a bit of explanation about all the parameters.

        read_more_text

This is the text to show a link to read more about a article.

        logo_path
        logo_text

These parameters are used for when you want to include an image logo or text in the header with your website's name.

        prefix_static_files

This is used when your website is not at the root of the URL for example

        http://localhost:1313/dbhq-wiki

Then your parameter must be set to

        prefix_static_files = "dbhq-wiki"

If not set like this the css files etc won't be loaded correctly.

        sidebar_tags

This must be set to 1 if you want a sidebar with all the tags listed. It can be set to 0.

        menu_tags

This must be set to 1 if you want a menu item with all the tags listed. It can be set to 0.

        pagination_number = 10
        pagination_older_text = "ouder"
        pagination_newer_text = "nieuwer"

These are parameters used for correct pagination. The first is to set how many articles will be shown per page. If you set this to 0 it will revert to default setting of 10 articles per page.

        pagination_older_text
        pagination_newer_text

These are for setting the links to older or newer pages full of articles.

## Frontmatter parameters

There are 3 parameters you must set in frontmatter of every article markdown page. These are the parameters

        type: "article"
        category: "config"
        tags: ['Gitweb', 'lighttpd', 'wit scherm' , 'blijven laden' , 'Linux', 'config']

Type must always be set to "article" for correct use of this template.
Category must be set to which root folder of your content tree you want the article to be shown.

In my case this can be "bits" or "installation" or "config".

The last one is Tags. This is used for creating tags for your article. These tags can be shown in a sidebar or as a menu item in the header (see config.toml parameters).