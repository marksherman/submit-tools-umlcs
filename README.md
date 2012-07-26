submit-tools-umlcs
==================

Instructor tools to aid in using the UMass Lowell Computer Science 'submit' system.
There are three scripts: getassignment, submitlog, and feedback.

For support, please contact msherman@cs.uml.edu

These scripts work, but are far from perfect. 

## getassignment
Extracts an assignment or collection of assignments from the submit directory to a destination folder for grading. 
While extracting, this script will copy in additional files from a skeleton directory. These additional files are used
for inserting test data, makefiles, and other tools the instructor wants to add to the student's assignment.
This script can extract a specific assignment by a specific student, or all submissions of a specific assignment.
Extraction of all of a single student's work is not yet implemented.

## submitlog
Easily checks the submission log. This is basically a shortcut to grep, with one big added feature: this script can
search for unique student submissions for a particular assignment. Calling it with -u option will find unique entries
that match the search string, ignoring students who re-submitted, and will count the total number of unique matching
submissions.

## feedback
Provides feedback to students by email. Sends an email tot he student based on their username, per assignment.
The grader may have text files, such as the student's source code, copied in to the message, and may leave custom comments.
This is the newest script, and is not as robust as the others. 

## System Context
These scripts depend on two major assumptions:
1. The University submit programd delivers student submissions to a specific directory, known as the SRC in these scripts.
2. The SRC directory is organized as SRC/assignment_name/student_name.tar

The scripts then expect you to have a different directory, the DST, where you want the student work expanded to, 
structured as such: DST/assignment_name/student_name/files*

## How to Use
Scripts should be placed in a folder within your home directory on the server. This folder must be added to your PATH.
I recommend ~/bin/ as the folder to put them in.
Each script has usage described in their header.
