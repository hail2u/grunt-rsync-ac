grunt-rsync-ac
==============

Run "[rsync][1] -aC --exclude-from=.rsyncignore".


INSTALL
-------

    $ npm install --save-dev rsync-ac

Of course, you need to install `rsync`.


CONFIGURE
---------

    module.exports = function (grunt) {
      grunt.initConfig({
        rsync: {
          options: {
            remote: 'user@example.com:~/Sites/example.com/'
          },

          main: {
            options: {
              dry_run: false,
              sync; true,
              progress: true
            }
          }
        }
      });
    };
    grunt.loadNpmTasks('grunt-rsync-ac');

Task name is `rsync`, not `rsync-ac` or `rsync_ac`. There is no need to
configure *src-dest* mappings. This Grunt plugin just run `rsync`.


### Excluding files

You can specify exclude patterns in `.rsyncignore` file. `.rsyncignore` file
must be placed in the same directory as a `Gruntfile.js` file. You can also
specify exclude patterns with:

  - `~/.cvsignore` file
  - A file set `$CVSIGNORE`
  - `.cvsignore` file in the same directory as a `Gruntfile.js`


### remote

*Required*: default value is `undefined`

A path to destination directory. This can be pointed to local directory.


### dry_run

*Optional*: default value is `true`

Enable `--dry_run` option or not. If this option sets to `true`, no changes made
to a remote directories.


### sync

*Optional*: default value is `false`

Enable `--delete` option or not. If this option sets to `true`, an extraneous
files will be deleted from destination directories.


### progress

*Optional*: default value is `false`

Enable `--progress` option or not. If this option sets to `true`, a progress
will be displayed during file transfer.


LICENSE
-------

MIT: http://hail2u.mit-license.org/2014


[1]: http://rsync.samba.org/
