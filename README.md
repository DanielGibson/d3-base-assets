D3 Base Assets
==============

This projects aims to create a standalone SDK for games based on the 
"dhewm3" Doom3 port (though it is useful with other ports as well),
so the Open Source Doom3 Engine can be used for  games without using
any proprietary media from the game itself.

Currently it's rather incomplete, especially the .def files for most
entities are missing.

The following files are not included and have to be copied from the 
original doom3 (or the demo) until dhewm3 has a working GLSL backend
and corresponding shaders that are under a free license:

>    glprogs/*

Probably it would also be useful to use some files from def/ to have
more entities available in the level editor.
I plan to have recreated versions of them with a free license in the 
future.

HOWTO use this
--------------

 * Clone dhewm3, see <https://github.com/dhewm/dhewm3/> (tested revision 
   df81835de056cd83c1692e0cc2ec432873f7ab2b)

 * Apply standalone.patch (`cd /path/to/dhewm3/ ; patch -p1 < /path/to/standalone/standalone.patch`)
 * Run cmake to create Makefiles
    - create build dir (in this example: /path/to/build)
    - `cd /path/to/build`
    - `cmake -DD3XP=NO -DBASE=NO /path/to/dhewm3/neo/`
      Note: the given options are just to speed up compiling and you may
        need additional options to make sure the standalone/ directory
        is used as data dir (see <https://github.com/dhewm/dhewm3/wiki/FAQ>)
 * Compile dhewm3. (on Linux: execute `make`)
 * Now you can execute dhewm3. You'll get a black screen, because there 
   is no main menu GUI yet.
   But console works as expected, so you can load the test map with 
   `map test` and quit the game with `quit`

Contributions are welcome!


Cheers,

Daniel (caedes)
