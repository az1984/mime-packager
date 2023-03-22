# mime-packager
MIME is Mac Installers Made Easy


## What MIME *is not*
By design, MIME is not a feature-by-feature match for any of the major Mac packaging suites (Munki, AutoPackger, etc.). It's built to be quicker to stand up than these--nearly as quick as a one-off using 'pkgtool'--but also be able to produce repeatable results.

## What MIME *is*
I wanted MIME to be a tool that is great when the situation calls for it.

The goal of MIME is to meet eight criteria:
- Sane. MIME plays nicely with hosting its package tree in a Git repo and doesn't require any odd workarounds, just 'sudo' access.
- Simple. MIME is built entirely out of ZSH, the default scripting langauge for Mac, and can operate 100% from whatever directory it's placed in. The script files are well-commented so a newbie to Mac administration can read them.
- Slender. MIME's advanced features are all optional, and the script detects missing pieces and goes around them, wherever possible. It doesn't require the user to have a code-signing cert, or define a package's architecture, or know how to automate with LaunchD, or have a Git repo, or... 
- Slick. Need to package something new? Create a subdirectory, create one folder, change two text files, and build.
- Scaleable. Need to package 100 somethings? Put them into their subdirectories and call the top level script.
- Scriptable. Other scripts can exploit MIME, and it can be put into a LaunchDaemon to run daily (or hourly), or even plugged into a Continous Integration, Continuos Development (CI/CD) system like Jenkins.
- Signing-aware. MIME can produce signed packages, and can even sign apps, if needed.
- Seperable. MIME is always ready to build all the packages in its subdirectories, but only builds the ones with a marker file.

## What MIME *can do*
Build a signed package from the files in a subdirectory.
Build a corresponding *uninstaller* package useful for Jamf or other MDMs.
Be initiated with a single command line invocation (optionally, one argument).
Log its operations thoroughly.


## What MIME *cannot do*

## Philosophy

MIME approaches packaging from the idea that packaging in-house requires full control of files, permissions, and scripts. MIME thinls it's better that a package take a few minutes longer to set up *the first time* you build it, but not need manual intervention for each version after.

## Origins
MIME grew out of a situation where I needed to be able to keep updated versions of a couple dozen packages.
- Apps that came in various formats
- Payload-less packages
- Organization specific files (logos, banners, etc.)

I only had Jamf Composer at my disposal, at the time. And it's...fine. It's supported by a company, and has a GUI, and all that good stuff. But Composer has some real limitations working with more than one package, and controlling things like the packages ID and version. Composer's strongest as a snapshot-based tool: Snapshot, install, snapshot again and you don't need to know anything about what the package puts where. It's not as good when you simply need to package one app that you already know the name of, and packaged a different version of last Tuesday.

Packaging new versions of common apps or altered versions of internal products, is a common task. Composer is not good for "I have a package I already know how to package, so just let me drop in the new version", because you have to do a new file, drag it in, check permissions, change the settings... It's like making a new Word Document every time you change someone's contact info.

## Strengths

- Generating revisions of packages you've created previously is quick, compared to Composer.
- Generating arbitrary packages (without upstream vendors) is simple, compared to AutoPkg.
- Acting on a number of packages at once is easy, and requires no more effort than acting on one package.

## Example

Let's say Firefox, Chrome, VLC, GIMP, and some marketing images all got updated this morning. We want our packages to have specific prefixes and names *com.ourcompany.pkg.[SOMETHING]* and we want the at-keyboard to be limited to the time it takes to eat a Snickers.

Composer:
- Launch Composer.
- Give it permission to access the disk.
- Drag the new GIMP to the sidebar of Composer.
- Look over the permissions and change appropriately. (It's probably owned by you, since you downloaded it).
- Hit Build as PKG
- Choose where to save it.




