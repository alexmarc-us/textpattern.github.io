\\n[mininav\_admin\_subtabs](/home/www/zendstudio/dokuwiki/bin/lib/exe/fetch.php?id=&media=mininav_admin_subtabs)

[![](/home/www/zendstudio/dokuwiki/bin/lib/exe/fetch.php?media=file:basic-prefs.png)](/home/www/zendstudio/dokuwiki/bin/lib/exe/detail.php?id=&media=file:basic-prefs.png)

The
[basic\_preferences](/home/www/zendstudio/dokuwiki/bin/doku.php?id=basic_preferences)
tab is the first most important panel in a new Textpattern site; it
(along with
[advanced\_preferences](/home/www/zendstudio/dokuwiki/bin/doku.php?id=advanced_preferences)
and
[language\_preferences](/home/www/zendstudio/dokuwiki/bin/doku.php?id=language_preferences))
is where you configure just about every aspect of how you want your site
to function on a regular basis.

The Basic Preferences panel is organized into two regions: “Publish” and
“Comments”. Both regions control the global site settings for article
publishing and article commenting, respectively.

**Note:** You can also control comments at the article level in the
[write](/home/www/zendstudio/dokuwiki/bin/doku.php?id=write) panel,
which effectively overrides the global setting on that given article.

### Publish {#publish .sectionedit1#publish}

The Publish preferences are an important aspect of site configuration
and used by Textpattern in other instances of your site, not the least
of which will be proper diagnostics monitoring, and how certain
information is presented to site visitors. There are a number of
different settings (Figure 2), which are discussed below.

[![](/home/www/zendstudio/dokuwiki/bin/lib/exe/fetch.php?media=file:admin-prefs-siteprefs-publish.gif)](/home/www/zendstudio/dokuwiki/bin/lib/exe/detail.php?id=&media=file:admin-prefs-siteprefs-publish.gif)

#### Site name {#site_name}

The “Site name” is simply the title of your website. For example your
personal blog called “The Big Bamboozler” or your business site called
“Willie Web Design”. By default, Textpattern fills this field with “Your
site”, which of course you should change.

#### Site slogan {#site_slogan}

The “Site slogan” is meant for a site subheading, motto, or other quip
that you fancy for your site. Considering the business name above,
*Willie Web Design*; Willie might like the line “Nothing but the best!”
in his branding, so he would put that in this field. The tagline is
optional; you do not have to ise it if nothing is appropriate for your
site.

**Note:** As of Textpattern version 4.0.7, the site slogan is
HTML-escaped before output. So the site slogan should be plain text,
with no HTML tags.

#### Site URL {#site_url}

The “Site URL” information is important for many reasons, not the least
of which is simply making your Textpattern site work. The Site URL will
be your Web site domain, without the

    http://

prefix and without a trailing forward slash (“/”); for example,

    www.example.com

or if you force dropping the “www” by way of rewrite rules, use

    example.com

.

If you install in a subdirectory, then it will be something like

    www.example.com/subdirectory

.

#### Production status {#production_status}

The production status provides a means for monitoring your site (or not)
as you work. There are three options, and each is specific to a
particular activity, as described below. (See the FAQ, [What does the
production status setting
do?](http://textpattern.com/faq/225/what-does-the-production-status-setting-do)
for a similar explanation.)

**Live**: This mode is primarily intended for production (live)
publishing; i.e. your site is designed and ready to go, and people on
the Internet are visiting it. In this mode, no error reporting or
[diagnostics](/home/www/zendstudio/dokuwiki/bin/doku.php?id=diagnostics)
information will be sent to the page. Generally, “Live” mode is
preferred, as it imposes the least overhead on the server. Furthermore,
you certainly don't want sensitive error messages to be showing up on
your live site. If your site is live to the world, always run it in live
mode. If you need to “Test” or “Debug”, you should either do that in a
secured directory or on a local server.

**Testing**: This mode is primarily intended for the initial setup and
design of a stable release of Textpattern. PHP error reporting on your
live site will be visible, as will errors encountered in
[Page](/home/www/zendstudio/dokuwiki/bin/doku.php?id=pages) templates
and [forms](/home/www/zendstudio/dokuwiki/bin/doku.php?id=forms), CSS,
configuration settings (e.g. the Preferences panel), or installing or
updating plugins.

In Testing mode, PHP error and warning messages will be displayed to the
user on public Web pages. Textpattern will attempt to warn about tag or
logic errors encountered in page templates and forms. Browser caching is
disabled. Performance information will be included in HTML comments at
the bottom of every Textpattern page; including:

-   the time it took the server to build the page (“Runtime”)
-   the number of MySQL queries executed
-   approximate peak memory usage

**Debugging**: This is mainly intended for diagnosing problems in
Textpattern [Page](/home/www/zendstudio/dokuwiki/bin/doku.php?id=pages)
templates,
[plugins](/home/www/zendstudio/dokuwiki/bin/doku.php?id=plugins) and PHP
code. PHP notices will be displayed, in addition to the errors and
warnings shown in Testing mode. Browser caching is disabled.

The following information will also be visible when you view the HTML
source of live pages:

-   the time it took the server to build the page (“Runtime”)
-   the number of MySQL queries executed
-   approximate peak memory usage
-   all Textpattern tags encountered while building the page (also known
    as a [Tag
    trace](http://textpattern.com/faq/165/diagnosing-template-problems))

Itâ€™s normal to see some PHP notices in “debug” mode. By itself, a PHP
notice is not an indicator that something is wrong; itâ€™s there to help
PHP developers find potential problems.

#### Time zone {#time_zone}

This control is where you set Textpattern's displayed time to be the
same as your local time. Textpattern calculates the local time based on
the server time (i.e. the time used by the server your Textpattern
package is installed on); thus, if the server time is not your local
time, you will need to adjust the time offset here.

The time system that is standard for all Internet-related
synchronizations is UTC ([Coordinated Universal
Time](http://en.wikipedia.org/wiki/UTC) ), which is the time system your
Web servers are likely using as well. When UTC is not offset at all, it
is equal to Greenwich Mean Time (GMT), and all global time zones are
then either offset forward or backward from this point. Hence,
Textpattern uses the notation of GMT plus the time offset value in this
control (Figure 3).

[![](/home/www/zendstudio/dokuwiki/bin/lib/exe/fetch.php?media=file:admin-prefs-publ-timezone.gif)](/home/www/zendstudio/dokuwiki/bin/lib/exe/detail.php?id=&media=file:admin-prefs-publ-timezone.gif)

Figuring the time offset for your own Textpattern installation is easy.
Look at the table below and find your respective time region in the
first column, “Time zone”. In the second column, “UTC Offset”, you will
see values with a “-” or “*” next to them, these are the number of hours
you will offset backward (“-”) or forward (“*”), with respect to UTC (or
similarly, GMT). For example, if you are living in France, your time
region will be “Central European Time”, which indicates one hour forward
of UTC. So in the time zone control you would select “GMT +01:00” to
adjust your UTC offset, and to ensure your articles reflect dates and
times accurate to where you are.

Table 1: Converting Universal Time to Standard Local Times\^ Time Zone\^
UTC Offset |

<table>
<col width="50%" />
<col width="50%" />
<tbody>
<tr class="odd">
<td align="left">
Pacific Standard Time\
UTC -8

</td>
<td align="left">
Mountain Standard Time\
UTC -7

</td>
</tr>
</tbody>
</table>
#### DST enabled? {#dst_enabled}

The “Daylight Savings” control is a pair of radio buttons for “Yes” and
“No” which allow you to adjust the UTC time established in the previous
section for daylight savings. Unfortunately, Textpattern will not do
this for you automatically based on your time zone settings, you need to
remember to do it yourself. If your region of the world follows a
daylight savings schedule (see [Worldwide Daylight
Saving](http://webexhibits.org/daylightsaving/g.html) ), you would turn
this setting on when daylight savings began, and turn it off when
daylight savings was over.

#### Date format {#date_format}

The “Date Format” control allows you to select how you want your date
and time formats to appear in your articles by default. There are
several options to choose from (Figure 4). Dates are output in your
written articles via the

    [[posted]]

tag.

[![](/home/www/zendstudio/dokuwiki/bin/lib/exe/fetch.php?media=file:admin-prefs-publ-dateformat.gif)](/home/www/zendstudio/dokuwiki/bin/lib/exe/detail.php?id=&media=file:admin-prefs-publ-dateformat.gif)

#### Archive date format {#archive_date_format}

The *Archive date format* is a drop-down menu that provides the exact
same options as the *Date format* menu (see Figure 4 above), but enables
you to create different date formats for the Archive section of your
site. This might be of interest depending on your site audience. As
before, the dates are output in your written articles (in this case in
your archival section) via the

    [[posted]]

tag.

#### Permanent link mode {#permanent_link_mode}

The *Permanent link mode* drop-down list is intended to make it easier
to establish flexible (or [Clean
URLs](/home/www/zendstudio/dokuwiki/bin/doku.php?id=glossary#clean_urls))
in your site, which in turn is a nice usability feature for your Web
site visitors. The drop-down list currently provides six different
options (Figure 5), one for “messy” URLs (which is the option for NOT
having clean URLs), and five for clean URLs; each having a specific path
format.

If you want clean URLs to work for your site, this is the very first
step to making it happen, by selecting one of the options other than
“messy.” However, it is usually not as simple as just selecting one of
these options to make clean URLs work. Getting clean URLs to work may
take a combination of steps, addressed in
[managing\_clean\_urls](/home/www/zendstudio/dokuwiki/bin/doku.php?id=managing_clean_urls).

[![](/home/www/zendstudio/dokuwiki/bin/lib/exe/fetch.php?media=file:admin-prefs-publ-permlink.gif)](/home/www/zendstudio/dokuwiki/bin/lib/exe/detail.php?id=&media=file:admin-prefs-publ-permlink.gif)

#### Use Textile {#use_textile}

Textile is a meta-formatting language that lets site authors format work
without having to know HTML completely. This option may be set to select
usage of Textile in articles; disable Textile but keep smart replacement
of line breaks and special characters; or disable article manipulation
entirely.

#### Logging

The “Logging” control allows you to select what kinds of visiting
activity Textpattern should record when such activity occurs. The
recorded information is displayed in the
[visitor\_logs](/home/www/zendstudio/dokuwiki/bin/doku.php?id=visitor_logs)
panel for you to review. This *Logging* control is a drop-down menu with
three options (Figure 6).

[![](/home/www/zendstudio/dokuwiki/bin/lib/exe/fetch.php?media=file:admin-prefs-publ-logging.gif)](/home/www/zendstudio/dokuwiki/bin/lib/exe/detail.php?id=&media=file:admin-prefs-publ-logging.gif)

-   **All hits**: By defaualt Textpattern will collect information for
    all site hits.
-   **Referrers only**: The *Referrers only* option will only record
    information about visitors from another location. This option is
    often the most popular choice because it allows you to see what kind
    of traffic your site is getting, while at the same time eliminating
    any log entries that might result from your own access to the site
    while, for example, making any site updates (generally you do not
    need to see your own activity on your site).
-   **None**: You can also choose to not log any information at all.

#### Accept comments? {#accept_comments}

This is a global setting (in this case for any article in any *Section*)
for whether or not you want to allow your articles to accept comments.
This is simply controlled with the “Yes” and “No” radio buttons,
respectively. This setting can be overridden on an article-by-article
basis in the
[write](/home/www/zendstudio/dokuwiki/bin/doku.php?id=write) tab as you
write new articles.

### Comments {#comments .sectionedit3#comments}

[![](/home/www/zendstudio/dokuwiki/bin/lib/exe/fetch.php?media=file:admin-prefs-siteprefs-comments.gif)](/home/www/zendstudio/dokuwiki/bin/lib/exe/detail.php?id=&media=file:admin-prefs-siteprefs-comments.gif)

If you set **Accept comments** to

    yes

, the bottom region of the Site Preferences view is where you establish
your global settings for article comments.

#### On by default? {#on_by_default}

Permission for commenting is regulated on a per-article basis. This
option controls the default setting for newly authored articles.

#### Default invite {#default_invite}

The text in this edit field will be automatically set in the comment
invitation field on the
[write](/home/www/zendstudio/dokuwiki/bin/doku.php?id=write) page for
new articles. The comment invitation may also be controlled on a
per-article basis.

#### Moderate comments? {#moderate_comments}

Controls whether or not comments should be immediately published to an
article (“No”), or if they should first be screened by a site
administrator for approval (“Yes”). Although having them published
immediately is more rewarding for the commenter, and less overhead
management for the site owner, there is a certain level of risk. One
might choose to moderate comments if there is a high degree of comment
spam activity, or if comments are tending to be inappropriate, indecent,
etc.

#### Disabled after {#disabled_after}

This is a selection of time periods during which comments will be
accepted for a given article. The time periods begin when a given
article is first published in *live* status. The duration options range
from 1 to 6 weeks and *never*.

**Note:** Keep in mind that the longer you keep comments open on a given
article, the more you increase the likelihood of comment spam. For this
reason, it is not recommended that you select “never”; however, the
decision is ultimately yours to make, as well as the management of
comment spam.

#### Automatically append comments to articles {#automatically_append_comments_to_articles}

If “Yes”, comments are added to articles irrespective of whether you add
a [comments](/home/www/zendstudio/dokuwiki/bin/doku.php?id=comments) tag
or not. If you see comments doubled up on an article page, either set
this to “No” or alter your comment form.

#### Comments mode {#comments_mode}

In “popup” mode, a tiny browser window will pop up for the viewer to
enter the comment. In “nopopup” mode, the main article page will change
to show the comment entry form.

#### Comments date format {#comments_date_format}

This control will select the date and time format for the posting time
of comments.

#### Present comments as a numbered list? {#present_comments_as_a_numbered_list}

If you want to use an HTML ordered list to display your user comments,
choose “Yes”. If you choose “No”, your comments will be output as blocks
of text without automatic numbers, thus numbering (if any) will have to
be done by you.

Some commenting plugins require this to be set to “No” before they work
properly

#### Mail comments to author? {#mail_comments_to_author}

If set to “Yes”, whenever a comment is made against an article, the
author will be emailed notification of the event, along with the
contents of the comment.