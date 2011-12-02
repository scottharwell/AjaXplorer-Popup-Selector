This is an attempt to create a plugin for Ajaxplorer that will allow you to create a form button to find a file on your server.
The purpose of this plugin is to create something similar to CKFinder's "popup" functionality with Ajaxplorer.

Copyright (C) 2011 Scott Harwell

This program is free software; you can redistribute it and/or
modify it under the terms of the GNU General Public License
as published by the Free Software Foundation; either version 2
of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program; if not, write to the Free Software
Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA  02110-1301, USA.

INSTRUCTIONS

To use this plugin: 

	1) Place the hook.popupchooser in your ajaxsplorer plugin directory.
	2) In your javascript (either inline or the file you are using to define your functions) create a callback function.
		-The function should be named 'ajaxplorerPopupCallback'
		-The body of the function should do what you want with the image path (such as set an input value)
	
	function ajaxplorerPopupCallback(filePath){
		$('.imagepath').val(filePath);
	}
		
	3) Create a function to popup the window:
		-The external_selector_type options must be set to popup
		-The relative_path parameter must be set and it must point to the ajaxplorer folder that stores your files
	
	function chooseFile(){
		var fbWindow = window.open(
		"/ajaxplorer/?external_selector_type=popup&relative_path=/files/",
		"ajaxplorer",
		width=600,
		height=500
	);
	
CHANGE LOG

12/2/2011

Ver .1

Plugin created with simple abilities to select a file from a popup window and have the file path sent back to a callback function.