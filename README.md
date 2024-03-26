followed basic webscraping tutorial
https://www.youtube.com/watch?v=QhD015WUMxE

most websites will block webscraping, legality, security
check the robots.txt file of the website to see what paths are disallowed for bots. It's important to follow these guidelines to avoid potential legal issues.

To find the robots.txt file of a website, you simply need to add /robots.txt to the root domain of the website.
https://example.com/robots.txt

User-agent: *
Disallow: /search/
Disallow: /*?customize_changeset_uuid=*
# START YOAST BLOCK
# ---------------------------
User-agent: * 
Disallow:

Sitemap: https://example.com/sitemap_index.xml
# ---------------------------
# END YOAST BLOCK

**User-agent: **: This line is targeting all web crawlers accessing the site. The asterisk () is a wildcard that applies to all robots, meaning the following rules apply to every web crawler that visits.

Disallow: /search/: This directive tells web crawlers not to crawl any URLs that start with /search/. It's a common practice to disallow search result pages from being indexed to prevent duplicate content issues or to prioritize the indexing of more important content.

Disallow: /?customize_changeset_uuid=: This line instructs robots not to crawl any URLs that include the parameter ?customize_changeset_uuid=. It's likely used to prevent crawling of temporary or session-specific URLs that wouldn't be useful in search engine indexes.

# START YOAST BLOCK and # END YOAST BLOCK: These comments indicate the start and end of a block of directives associated with the Yoast SEO plugin, which is commonly used on WordPress sites to manage SEO settings. Comments in robots.txt files (anything following a # on a line) are ignored by crawlers and are used for human readability.

Within the Yoast block:

**User-agent: ***: Again, this targets all robots, but it's specified again within the Yoast block for clarity or organizational purposes.
Disallow:: Interestingly, this Disallow directive is empty, meaning it doesn't specify anything to disallow for crawlers. It effectively cancels any Disallow command for the User-agent: * it applies to, which in this context, seems redundant or to ensure clarity that all content not previously disallowed should be accessible to crawlers.
Sitemap: https://example.com/sitemap_index.xml: This directive points crawlers to the website's XML sitemap—a file that lists all URLs on the site along with additional metadata. This helps search engines to more intelligently crawl the site. Sitemaps are particularly helpful for ensuring that search engines are aware of all the content on a site, especially new or updated content.
