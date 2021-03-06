# Viewing CloudTrail Events in the CloudTrail Console<a name="view-cloudtrail-events-console"></a>

You can use the CloudTrail console to view the last 90 days of recorded API activity and events in an AWS Region\. You can also download a file with that information, or a subset of information based on the filter and time range you choose\. You can customize your view of event history by selecting which columns are displayed in the console\.

For information about which events are recorded, see [Services Supported by CloudTrail Event History](view-cloudtrail-events-supported-services.md) and [Resource Types Supported by CloudTrail Event History](view-cloudtrail-events-supported-resource-types.md)\.

**To view CloudTrail events**

1. Sign in to the AWS Management Console and open the CloudTrail console at [https://console\.aws\.amazon\.com/cloudtrail/home/](https://console.aws.amazon.com/cloudtrail/home/)\.

1. In the navigation pane, choose **Event history**\. 

A list of events appears in the content pane with the latest event first\. Scroll down to see more events\. Events that are not recorded do not appear\.

For a list of supported services and regions, see [Services Supported by CloudTrail Event History](view-cloudtrail-events-supported-services.md) and [Regions Supported by CloudTrail Event History](view-cloudtrail-events-supported-regions.md)\.



## Displaying CloudTrail Events<a name="displaying-cloudtrail-events"></a>

You can customize the display of event history by selecting which columns to display in the CloudTrail console\. By default, the following columns are displayed:

+ **Event time**

+ **User name**

+ **Event name**

+ **Resource type**

+ **Resource name**

You cannot change the order of the columns\.

**To customize the columns displayed in event history**

1. Sign in to the AWS Management Console and open the CloudTrail console at [https://console\.aws\.amazon\.com/cloudtrail/home/](https://console.aws.amazon.com/cloudtrail/home/)\.

1. In the navigation pane, choose **Event history**\. 

1. Choose the gear icon\.

1. In **Show/Hide Columns**, select the columns you want to display\. Clear the columns you do not want to display\. When you have finished, choose **Save**\.

## Filtering CloudTrail Events<a name="filtering-cloudtrail-events"></a>

 You can filter events by the following attributes\. You can filter by time range and one other attribute\.

** Event ID **  
The CloudTrail ID of the event\. Each event has a unique ID\.

** Event name **  
The name of the event\. For example, you can filter on IAM events, such as `CreatePolicy`, or Amazon EC2 events, such as `RunInstances`\.

** Event source **  
The AWS service to which the request was made, such as `iam.amazonaws.com` or `s3.amazonaws.com`\. You can scroll through a list of event sources after you choose the **Event source** filter\. 

** Resource name **  
The name or ID of the resource referenced by the event\. For example, the resource name might be "auto\-scaling\-test\-group" for an Auto Scaling group or "i\-1234567" for an EC2 instance\.

** Resource type **  
The type of resource referenced by the event\. For example, a resource type can be `Instance` for EC2 or `DBInstance` for RDS\. For more information, see [Resource Types Supported by CloudTrail Event History](view-cloudtrail-events-supported-resource-types.md)\.

** Time range **  
The time range in which you want to filter events\. You can filter events for the last 90 days\.

** User name **  
The name of the user referenced by the event\. For example, this can be an IAM user\.

If there are no events logged for the attribute or time that you choose, the results list is empty\. You can apply only one attribute filter in addition to the time range\. If you choose a different attribute filter, your specified time range is preserved\.

The following steps describe how to filter by attribute\. 

**To filter by attribute**

1. To filter the results by an attribute, choose **Select attribute**, and then type or choose a value in the **Enter lookup value** box\.

1. To remove an attribute filter, choose the **X** on the right of the attribute filter box\.

The following steps describe how to filter by a start and end date and time\.

**To filter by a start and end date and time**

1. To narrow the time range for the events that you want to see, choose **Select time range**\.

1. To remove a time range filter, choose the calendar icon on the right of the **Time range** box, and then choose **Remove**\.

## Viewing Details for an Event<a name="viewing-details-for-an-event"></a>

1. Choose an event in the results list to show its details\.

1. If the event referenced more than one resource, the additional resources are listed at the bottom of the details pane\. 

1. Some referenced resources have links\. Choose the link to open the console for that resource\.

1. Choose **View Event** in the details pane to view the event in JSON format\. 

1. Choose the event again to close the details pane\. 

## Downloading Events<a name="downloading-events"></a>

You can download recorded event history as a file in CSV or JSON format\. Use filters and time ranges to reduce the size of the file you download\. For more information about which events are recorded, see [Services Supported by CloudTrail Event History](view-cloudtrail-events-supported-services.md) and [Resource Types Supported by CloudTrail Event History](view-cloudtrail-events-supported-resource-types.md)\.

**Note**  
CloudTrail event history files are data files that contain information \(such as resource names\) that can be configured by individual users\. Some data can potentially be interpreted as commands in programs used to read and analyze this data \(CSV injection\)\. For example, when CloudTrail events are exported to CSV and imported to a spreadsheet program, that program might warn you about security concerns\. You should choose to disable this content to keep your system secure\. Always disable links or macros from downloaded event history files\.

1. Specify the filter and time range for events you want to download\. For example, you can specify the event name, `StartInstances`, and specify a time range for the last three days of activity\.

1. Choose the ![\[download icon\]](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/images/history-download.png) and then choose **Export to CSV** or **Export to JSON**\. The download starts immediately\.
**Note**  
Your download might take some time to complete\. For faster results, before you start the download process, use a more specific filter or a shorter time range to narrow the results\.

1. After your download is complete, open the file to view the events that you specified\.

1. To cancel your download, choose **Cancel download**\.

## Viewing Resources Referenced with AWS Config<a name="viewing-resources-config"></a>

AWS Config records configuration details, relationships, and changes to your AWS resources\. 

On the **Resources Referenced** pane, choose the ![\[AWS Config timeline icon\]](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/images/config-timeline.png) in the **Config timeline** column to view the resource in the AWS Config console\.

If the ![\[AWS Config timeline\]](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/images/config-timeline-gray.png) icon is gray, AWS Config is not turned on, or it's not recording the resource type\. Choose the icon to go to the AWS Config console to turn on the service or start recording that resource type\. For more information, see [Set Up AWS Config Using the Console](http://docs.aws.amazon.com/config/latest/developerguide/gs-console.html) in the *AWS Config Developer Guide*\.

If **Link not available** appears in the column, the resource can't be viewed for one of the following reasons:

+  AWS Config doesn't support the resource type\. For more information, see [Supported Resources, Configuration Items, and Relationships](http://docs.aws.amazon.com/config/latest/developerguide/resource-config-reference.html) in the *AWS Config Developer Guide*\.

+ AWS Config recently added support for the resource type, but it's not yet available from the CloudTrail console\. You can look up the resource in the AWS Config console to see the timeline for the resource\.

+ The resource is owned by another AWS account\.

+ The resource is owned by another AWS service, such as a managed IAM policy\.

+ The resource was created and then deleted immediately\.

+ The resource was recently created or updated\.

**Example**  

1. You configure AWS Config to record IAM resources\.

1. You create an IAM user, Bob\-user\. The **Event history** page shows the `CreateUser` event and Bob\-user as an IAM resource\. You can choose the AWS Config icon to view this IAM resource in the AWS Config timeline\.

1.  You update the user name to Bob\-admin\. 

1. The **Event history** page shows the `UpdateUser` event and Bob\-admin as the updated IAM resource\.

1. You can choose the icon to view the Bob\-admin IAM resource in the timeline\. However, you can't choose the icon for Bob\-user, because the resource name changed\. AWS Config is now recording the updated resource\.

To grant users read\-only permission to view resources in the AWS Config console, see [Granting Permission to View AWS Config Information on the CloudTrail Console](grant-custom-permissions-for-cloudtrail-users.md#grant-aws-config-permissions-for-cloudtrail-users)\.

For more information about AWS Config, see the [AWS Config Developer Guide](http://docs.aws.amazon.com/config/latest/developerguide/)\.