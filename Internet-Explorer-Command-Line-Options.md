```
iexplore.exe [ -embedding ] 
             [ -extoff ] 
             [ -framemerging ] 
             [ -k ] 
             [ -noframemerging ]
             [ -nohangrecovery ]
             [ -private ] ]
             [ URL ]
```
### Command-line option:
| Option | Description |
|-----|-----|
| -embedding | Starts Internet Explorer through OLE embedding (such as the WebBrowser Control). |
| -extoff | Internet Explorer 7 and later versions. Starts Internet Explorer in No Add-ons mode, which you can use to troubleshoot problems with browser add-ons. For more information, see Troubleshooting Internet Explorer Add-ons. |
| -framemerging | Internet Explorer 8 and later versions. Enables Internet Explorer to opportunistically merge new frame processes into existing frame processes. For more information, see Explorer 8 and Reliability. |
| -k 	Starts Internet Explorer in kiosk mode. The browser opens in a maximized window that does not display the address bar, the navigation buttons, or the status bar. |
| -noframemerging | Internet Explorer 8 and later versions. Prevents Internet Explorer from opportunistically merging new frame processes into existing frame processes. |
| -nohangrecovery | Internet Explorer 9. Prevents Internet Explorer from restarting a tab when it stops responding. This option enables application developers to use debugging tools to investigate problems with Browser Helper Objects (BHOs), Microsoft ActiveX controls, and other browser extentions. |
| -private | Internet Explorer 8 and later versions. Starts Internet Explorer with InPrivate Browsing set to active. For more information, see Blog: Online Privacy, Tracking, and InPrivate Filtering. |
| URL | Navigates to the page or resource that you specify as URL, after Internet Explorer opens. |