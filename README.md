# mime-packager
MIME is Mac Installers Made Easy

## What MIME *is*
- Simple. Need to package something? Create a subdirectory, change two text files, and build.
- Scaleable. Need to package 1000 somethings? Put them in a subdirectory and call the top level script.

## What MIME *is not*

## What MIME *can do*

## What MIME *cannot do*

## Philosophy

MIME approaches packaging from the idea that packaging in-house requires full control of files, permissions, and scripts. MIME thinls it's better that a package take a few minutes longer to set up *the first time* you build it, but not need manual intervention for each version after.


## Origins
MIME grew out of a situation where I needed to be able to keep updated versions of a couple dozen packages.
- Apps that came in various formats
- Payload-less packages
- Organization specific files (logos, banners, etc.)

I only had Jamf Composer at my disposal, at the time. And it's...fine. It's supported by a company, and has a GUI, and all that good stuff. But Composer has some real limitations working with more than one package, and controlling things like the packages ID and version. 

What it's *best* for is something you've never pacakged before. Composer's best as a snapshot-based tool: Snapshot, install, snapshot again and you don't need to know anything about what the package puts where.

It's not as good for "I have a package I already know how to package, but I need to package the new version", because you have to do a new file, drag it in, change the settings... It's like making a new Word Document every time you change someone's contact info.

Composer is *terrible* if you have multiple packages to keep updated. Let's say Firefox, Chrome, VLC, GIMP, and some marketing images all got updated this morning. 

Composer:
Drag the new GIMP to the sidebar of Composer.



