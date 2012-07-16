ops4j_pax_war_archetype_fzlbpms_template
========================================

This project is part a academic term paper.
Its main purpose is be a base model to another funcional projects.
To achieve this, the "mvn archetye:from-project" will be issued to create a archetype.

This can be interesting for others because its configuration.
This is configured to be a war (serlvet 2.5) package that can be deployed in a web container and in a osgi container too.
This is based on war archetype cited in http://blog.nanthrax.net/tag/pax-web/.

Beside this, it was based on https://github.com/csnover/dojo-boilerplate/
The (maybe) interesting point here is that, beside build benefits:
the build will ocurr automatically at the build project
if the dojo sdk was not present, it will be downloaded automatically base on <dojo.version> pom propertie.

I am learning all this technology, so any help is well accepted.
This is a snapsht and be testing.

#-----------------------------------------------------------#
HOW TO BUILD...
#-----------------------------------------------------------#
1) For a complete build

Check the ${dojo.app.skip_build} pom propertie:
 = true result in build.sh skip the dojo app building process.
 = false in order to build.sh proceed dojo app build.


Go to the build pom section, and check if
wagon-maven-plugin skyp configuration tag is marked to false in order to be assured that the
dojo sdk will be downloaded and be avaible to be unpackaged and extracted to correct
folders expected by build.sh. Theese folders are 
	webapp/resoureces/js/dojo
	webapp/resoureces/js/dijit
	webapp/resoureces/js/dojox
	webapp/resoureces/js/util
	To be documented: the unpack and copy tasks are proceeded by antrun plugin tasks.
	Note1: the dojo sdk version you want to download is configure using ${dojo.version} pom property 
	Note2: If dojo sdk is present, is ok to setup this skip tag value to true. (default is false).
	
	
	
check ${dojo.app.use_rhino_or_node} pom property value
 = node (or any other value): node will be used to proceed with dojo app build
 = rhino: rhino will be used
 
 
some another notes:
mvn clean command will clean  webapp/resoureces/js/dist too.

 

