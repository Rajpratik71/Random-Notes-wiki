== Problem ==
You receive the following error when trying to install the Android Development Tools (ADT) plugin into Eclipse Juno:

 Cannot complete the install because one or more required items could not be found. 
 Software being installed: Android Development Tools 20.0.3.v201208082019-427395 (com.android.ide.eclipse.adt.feature.group 20.0.3.v201208082019-427395)
 Missing requirement: Android Development Tools 20.0.3.v201208082019-427395 (com.android.ide.eclipse.adt.feature.group 20.0.3.v201208082019-427395) requires 'org.eclipse.wst.sse.core 0.0.0' but it could not be found

[[File:Eclipse_Error_1.jpg]]

The ADT plugin requires the 'org.eclipse.wst.sse.core 0.0.0' plugin.

== Solution ==
Add the Juno download Repository.

Click the Add button and paste in the following URL: http://download.eclipse.org/releases/juno

[[File:Eclipse_Error_2.jpg]]

Then make sure that the "Contact all update sites durring install to find required software" checkbox is selected.

[[File:Eclipse_Error_3.jpg]]

The ADT plugin installation should now work.
