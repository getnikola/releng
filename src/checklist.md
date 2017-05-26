# Nikola Release Checklist (v14/2017-05-26)

## Requirements

In order to create a release, you need a bit of free time, ZSH installed, and a GPG setup.

## Preparation

 * <input type="checkbox"> If you have a local clone of the releng repo: `git pull` first, refresh the page if necessary
 * <input type="checkbox"> Get into the Nikola repo, make sure you are on the `master` branch and run `git pull origin master`
 * <input type="checkbox"> Pick a reasonable version number. Increase the last number (patch) or, if the changes *really* are significant, increase the second number (minor).

## Writing announcements

All announcements must include the *Greeting*, *What is Nikola?*, *Downloads*, and *Changes* blocks, in that order. Use the announcements in the Release Engineering repo as a template.

You may also add a *Key Changes since last release* block after *What is Nikola?*.

 * <input type="checkbox"> Write an announcement for GitHub Releases. It should use Markdown syntax and no word wrap.
 * <input type="checkbox"> Write an announcement for e-mail. It should use reST-esque syntax, with word wrap at 70 columns.
 * <input type="checkbox"> Write an announcement for the Nikola blog. Use `nikola new_post -et "Nikola v$VERSION is out"'!' -i path/to/blog.rst --tags 'nikola, planet, python, programming, release'` to import the announcement template (which you should then edit). Make sure to set the author name to your real name.

## Release!

Run the release script and hope everything works fine:

 * <input type="checkbox"> `scripts/release`

## GitHub Releases

 * <input type="checkbox"> Create a GitHub release for this version by running `scripts/github-release.py` (pass announcement filename and ``v$VERSION`` as arguments)

## GitHub Issues

 * <input type="checkbox"> Create milestone for next release
 * <input type="checkbox"> Move outstanding issues to milestone for next release
 * <input type="checkbox"> Close milestone for this release

## Local update

 * <input type="checkbox"> Use `pip install -e .` to reinstall Nikola from Git in your virtualenv (if applicable)

## Website update

 * <input type="checkbox"> Optionally regenerate the `cerulean` theme: `nikola bootswatch_theme -s cerulean -n cerulean`
 * <input type="checkbox"> Build and deploy the site
 * <input type="checkbox"> Commit and push your changes to GitHub

## E-mails

 * <input type="checkbox"> Send the e-mail announcement to <nikola-discuss@googlegroups.com> and <python-announce-list@python.org>. You should sign it with GPG if possible.

## Finishing up

 * <input type="checkbox"> Give yourself a pat on the back!
 * <input type="checkbox"> If you have access to the AUR packages, update them (if not, wait for Chris to handle this)
 * <input type="checkbox"> If you have access to the Snapcraft packages, update them (if not, wait for Roberto to handle this)
