^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package sicks300
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1.2.1 (2018-09-10)
------------------

1.2.0 (2018-03-21)
------------------

1.1.0 (2018-03-21)
------------------
* Merge pull request `#7 <https://github.com/strands-project/sicks300/issues/7>`_ from imoverxyz/add-missing-commits
  Add missing commits
* Merge remote-tracking branch 'origin/master' into HEAD
* Merge pull request `#9 <https://github.com/strands-project/sicks300/issues/9>`_ from prarobo/master
  Avoid serial port open command from hanging
* Adding additional serial port flags to fix the serial port hanging on open
* Merge pull request `#6 <https://github.com/strands-project/sicks300/issues/6>`_ from strands-project/upstream-import
  Upstream import
* removed external maintainer
* Merge pull request `#8 <https://github.com/strands-project/sicks300/issues/8>`_ from prarobo/master
  Bugfix to support custom input frames
* Bugfix to support custom input frames
* Merge pull request `#7 <https://github.com/strands-project/sicks300/issues/7>`_ from larics/master
  Improvements to the readData function
* Merge pull request `#2 <https://github.com/strands-project/sicks300/issues/2>`_ from ojura/master
  Rewrite of the serial communication
* Change debug messages severity to ROS_DEBUG
* Use read blocking, eliminate the main loop timer
  With cyclades-serial-client, the interface does not actually block until
  all requested bytes have been read, but the package is read in about 10
  iterations of the main loop, which is an acceptable amount of "busy waiting".
* Add a connect hook
  This system command is executed before the laser connection is opened (also
  on reconnection). It is specified using the optional ROS parameter
  ~connect_cmd (default: none).
* Make ROS node handles node class member variables
  They shouldn't go out of scope when the node constructor is finished
* Improve reconnection logic, add a warning for stale measurements
  Stale measurements can happen with a serial->ethernet converter, we detect
  this by querying the number of bytes in the RX buffer.
* Perform a rewrite of the readData function
  - fix the occasional bad checksum issue, which was occuring due to a race
  condition caused by a bad check if enough bytes had been received
  - add a map of the laser data packet layout in the comments
  - removed ugly offset constants in favour of a more systematic approach
  to addressing elements of the data packet
  - introduce a sane way of calculating the total packet size and addressing
  the differences between the two protocol versions
  - previous also fixes discarding bytes of the processed packet in protocol
  version 1.03, when 10 bytes from the end of the packet weren't discarded;
  now the find header loop doesn't have to go through them
  - fix comment typo in sicks300.h
  - release memory claimed by m_ranges
* Update .gitignore, minor cosmetic code tweaks
* Minor reformat of code indentation
* Add some debugging output
* Convert error messages in serial communication to use ROS_ERROR
* Add reading of additional scan metadata
  i.e. the scan number and the telegram number
* Contributors: Damjan Miklic, Dimitri Bohlender, Gary Servin, Juraj Oršulić, Marc Hanheide, Prasanna Kannappan, prarobo, stribor14

1.0.6 (2017-06-28)
------------------
* removed external maintainer
* Contributors: Marc Hanheide

1.0.5 (2014-11-05)
------------------
* Merge pull request `#5 <https://github.com/strands-project/sicks300/issues/5>`_ from strands-project/upstream_merge
  Upstream merge
* Merge branch 'master' of https://github.com/bohlender/sicks300 into upstream_merge
* Merge pull request `#3 <https://github.com/strands-project/sicks300/issues/3>`_ from cburbridge/master
  Allow user to select reduced field of view.
* Merge pull request `#4 <https://github.com/strands-project/sicks300/issues/4>`_ from strands-project/prepare_for_release
  Prepare for release
* Merge pull request `#2 <https://github.com/strands-project/sicks300/issues/2>`_ from strands-project/merge_prepare_for_release
  Merge prepare for release
* Merge remote-tracking branch 'origin/prepare_for_release' into merge_prepare_for_release
* merged
* added Marc Hanheide as additional maintainer
* - added changelog
  - added <cstddef> for new gcc
  - added unistd.h for gcc
* Allow user to select reduced field of view.
  This commit replaces the bool 'reduced_fov' parameter with double 'field_of_view'. This allows the user to select what angle of view the laser should publish. Setting this to 180 will have the same effect as setting reduced_fov to 1 previously. Setting it to 260 will remove 5 degrees from the start and end of the scan.
* Contributors: Dimitri Bohlender, Marc Hanheide, cburbridge

* - added changelog
  - added <cstddef> for new gcc
  - added unistd.h for gcc
* Contributors: Marc Hanheide

* Merge pull request `#2 <https://github.com/strands-project/sicks300/issues/2>`_ from larics/master
  Catkinized the package
* Updated CMakeLists.txt and package.xml.
* Catkinized the package.
* Update README.md
* Fixed typo and added more explicit credits.
* Modified description and authors in manifest file
* Update README.md
* Create README.md
* - Adapted original implementation to support both the old (v.1.02) and the new (v.1.03) protocols for continuous data output of the SICK S300 Professional
  - Fixed a bug which caused the header start to be off (this caused unnecessary CRC failures)
  - Adapted copyrights/license stuff
* 
* 
* 
* 
* Contributors: Damjan Miklic, Dimitri Bohlender, dbohlender, torstenfiolka

* Merge pull request `#2 <https://github.com/strands-project/sicks300/issues/2>`_ from larics/master
  Catkinized the package
* Updated CMakeLists.txt and package.xml.
* Catkinized the package.
* Update README.md
* Fixed typo and added more explicit credits.
* Modified description and authors in manifest file
* Update README.md
* Create README.md
* - Adapted original implementation to support both the old (v.1.02) and the new (v.1.03) protocols for continuous data output of the SICK S300 Professional
  - Fixed a bug which caused the header start to be off (this caused unnecessary CRC failures)
  - Adapted copyrights/license stuff
* 
* 
* 
* 
* Contributors: Damjan Miklic, Dimitri Bohlender, dbohlender, torstenfiolka
