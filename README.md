![Mou icon](http://vadim-dev.s3.amazonaws.com/formbuilder2/formbuilder2_logo.png)

***

FormBuilder 2 is a Craft CMS plugin that lets you create & manage forms for your front-end. Entries get stored to database so you can easily view your submission or export them.

***

Note: Craft 2.5 will be released on December 1st. Looks like the admin UI is similar to what I built for this plugin. If I keep it the way it is now, it'll just look weird with 2 sidebars. Soooooo after just releasing this I realize that I'll need to rethink UI. Besides the UI change I'll need to make sure everything works as it should with 2.5. You can use this now, but I just wanted to make sure you guys know it might look different in a month. 

***

#### Dashboard [Screenshot](http://vadim-dev.s3.amazonaws.com/formbuilder2/screenshots/Dashboard.jpg)

Here you can have an overview of how many forms you have as well as total entries count.

#### Forms [Screenshot](http://vadim-dev.s3.amazonaws.com/formbuilder2/screenshots/Forms.jpg)

This section will show you a list of all the forms you created. You can preview things like form name, handle name, how many entries form has, and perfect actions such as copying form handle name and deleting the form.

#### Entries [Screenshot](http://vadim-dev.s3.amazonaws.com/formbuilder2/screenshots/Entries.jpg)

Preview all submission. You can filter submission by forms. For each submission you have an overview which form submission belongs to, date of submission, link to preview submission and if submission has any file uploads it'll display number of uploads.

***

# Front-End Template Usage

Take a look at `sampleForm.twig` for required code. You will need to copy everything in that file and paste it to where you want to display your form.

***

# Spam Protection

There are 2 options for spam protection, Time Submissions and Honeypot method.

#### 1. Time Submission

Time submission will prevent spam bots for submitting the form too quickly. You need to enter a time (seconds) it should take a real person to submit a form. Typically 3 seconds is good enought.

##### 2. Honeypot Method

With honeypot there is a hidden field that should be left blank. When spam bots run through the form they tend to fill out all the fields. If the honeypot field will get field the submission will fail. Real people will not be able to fill out this field so the form will submit succesfully.


***

# File Uploads

Create an Asset field and add it to your form. You need to select **Has File Uploads** box when creating your form to make sure files get submitted. 

***

# Email Notifications

Set up your forms to send email notifications to any emails you like. Email notifications can be customized a little. You can choose between plain text or an HTML email template. For each option you can add an optional body and footer text. If you going with HTML template you can upload a custom logo, pick background color and add container width.

***



# Creating Forms

Hit `Create New Form` to creat a new form.

* **Form Settings**
  * `Form Name` - Give your form a name
  * `Handle` - Will be autogenerated, you can change to a custom one
  * `Use Custom Redirect` - Select this option if you want a custom redirect page (thank-you page). Redirect URL is required and is relevant to your domain.
  * `Has File Uploads` - Select this if your form has file uploads
  * `Use AJAX` - Select this if you want your form to submit using javascript without page refresh. `Note:` You can't use Has Form Uploads and Ajax together yet (workign on it).
* **Spam Protection**
  * `Timed Submissions` - Select this and set time in seconds. Timed submissions will prevent quick spam robots from submitting too quickly. 
  * `Honeypot` - Select this option to try and catch spam robots using a honeypot method. Hidden field in the form needs to be left empty, if filled the form will fail (most robots will fill this field).
* **Messages**
  * `Success Message` - Enter form success message. If you form has custom redirect this is useless.
  * `Error Message` - Enter generic error message if submission has errors this will be displayed along with the field specific error message (`Ex: Your Name cannot be empty`).
* **Email Notifications**
  * `Notify Admin of Submission` - Select this if you want to send email notification of submission.
  * `Notification Email` - Enter email where the notification should be sent to. you can enter multiple emails separated by a comma `,`
  * `Email Subject` - Enter subject line for email notification
  * `Include Submission Data` - You can tick this option if you like the email to contain the submission content.
  * `Email Template` - You can pick if you want email to be Text Only or HTML Template.
  * `Text Only` - With this option you can enter optional `Body Copy` and `Footer Copy`.
  * `HTML Template` - With this option you can upload a `custom logo`, give email template a `custom background color`, give a `container width` as well as optional `Body Copy` and `Footer Copy`.
* **Fields**
  * `Add Fieldset Tab` - Click this to add a fieldset. Then drag and drop fields into those fieldsets. You can also drag predefined fieldsets with fields form the `Unused Fields` section. If you dont see any fields you will need to head over to `admin/settings/fields` to create some fields.
 
***

# Supported Fields

Here's a list of currently supported fields. Unlike FormBuilder there are no more custom fieldtypes, you only need to use Craft's predefined fields.

* Plain Text
* Checkboxes
* Radio Buttons
* Dropdowns (Select Options)
* Multi Select
* RichText (WYSIWYG)
* Light Switch (Toggle)
* Color (Color Picker)
* Date
* Number
* Assets (Only local file uploads supported for now, no s3, no rackspace)

***

## Issue Tracking and Bug Reporting

If you have found a bug or would like to request a feature please use [Github's Issues](https://github.com/roundhouse/FormBuilder-2-Craft-CMS/issues) to report and track issues.

## Contributing

For contributing use the "fork-and-pull" Git workflow. In general use the following steps **(Be sure to merge the latest from "master" before making a pull request)**:

* Fork the repo on GitHub
* Commit changes to a branch in your fork
* Pull request "development" with your changes


## License

[The MIT License (MIT)](http://opensource.org/licenses/MIT)

Copyright (c) 2014 Roundhouse Agency
Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.