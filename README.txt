Solutions for Open Land Administration (SOLA) is an open source
software system that aims to make computerised cadastre and
registration systems more affordable and more sustainable in developing
countries. For more information refer to www.flossola.org. 

SOLA uses 10 Git repositories for managing its code base. These
repositories are:

1) code      - This repository. Contains the Main POM file and
               additional supporting files. This Git repository acts
               as the super/parent repositories for all the other SOLA
               Git repositories. 
2) clients   - Contains the Clients Desktop and Clients Admin projects
               along with the other client side projects. Attached as
               the clients subdirectory of the code repository. 
3) common    - Contains only the Common Utilities project. Attached as
               the common/common subdirectory of the code repository. 
4) rules     - Contains only the Common Rules project. Attached as the 
               common/rules subdirectory of the code repository. 
5) help      - Contains only the Common Help project. Attached as the 
               common/help subdirectory of the code repository. 
6) messaging - Contains only the Common Messaging project. Attached as
               the common/messaging subdirectory of the code
               repository. 
7) boundary  - Contains the Web Service Boundary projects. Attached as
               the services/boundary subdirectory of the code
               repository. 
8) services  - Conatins the EJB and common service projects. Attached
               as the services subdirectory of the code repository.
9) database  - Contains the SOLA database scripts. Attached relative to
               the code repository in the ../database directory.
10) test     - Contains the Fitness and Performance test projects. 
               Attached in the test subdirectory of the code 
               repository. 

Each repository can be managed independently, although when a change
spans more than one repository, ensuring the changes remain
synchronized across the repositories can be difficult. Also tasks such
as pushing and pulling from GitHub can be extremely repetitive as they
may need to be done up to 10 times (once for each repository). Git does
not provide any really good tools for managing multiple repositories as
one. To effectively manage git command across multiple SOLA Git
repositories, the gits (Git Slave) script can be used. This script can
issue a git command to all nested/slave repositories and is particularly
useful for committing changes and pushing and pulling from the GitHub
repositories. 

The gits script has been included in the root folder of the code
repository. To use gits, open the Git Bash Shell and cd to the root of
the code repository. At the prompt type gits <any git command> to issue
a git command that will apply to the super repository and all slave
repositories. For addtional details on using gits, see the Git Slave
tutorial (http://gitslave.sourceforge.net/tutorial-basic.html) as well
as the Git Slave topic on the SOLA Wiki 
(http://www.flossola.org/wiki/Git:Git_Slave).

NOTE: You are not required to use gits. You can still deal with each
repository independently using the Git GUI, Git Bash and/or any
combination of gits, Git GUI and Git Bash that you choose.

One issue with using Git Slave to push and pull from GitHub is that the
gits pull and gits push commands prompt for the user's GitHub password
or every nested repository (i.e. up to 10 times). To avoid this it is
possible to configure ssh-agent within your Git Bash session. To do
this open the Git Bash shell and cd to the git-support subdirectory of
the code repository. This folder contains the .bashrc file. Using the Git
Bash shell copy the .bashrc file to your HOME directory (cp .bashrc ~).
Restart the Git Bash shell to launch the ssh-agent. You will be
prompted for your GitHub password and this will be stored for future
use. For further details regarding ssh-agent refer to the GitHub help
(http://help.github.com/ssh-key-passphrases/ - Auto-launching ssh-agent
on msysgit). 

The Git Slave home page is http://gitslave.sourceforge.net/. The version
currently used by SOLA is 2.0.2. 
			   
			  
