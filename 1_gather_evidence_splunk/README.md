# Splunk Workflow

## Download the Dataset

## Upload the dataset to Splunk

## Let the Splunking Begin

1. DATA OVERVIEW: Basic overview of the data to understand the type of events and frequency of each:
    ```s
    index="main" source="AWS_S3_HoneyBucketLogs.csv" host="ubuntu"
    | stats count by "Event Name"
    | sort - count
    ```
    <br />
    <br />


1. Analyze Specific Event Types: Focus on the details of each event type, particularly any that involve access or modifications, such as PutObject, ListObjects, or HeadBucket:
    ```s    
    index="main" source="AWS_S3_HoneyBucketLogs.csv" host="ubuntu"
    | stats count by "Event Name", "Source IP"
    | sort - count
    ```
    Note: I found a that the there is a high count of Source IP's to the Event Names: HeadBucket and ListObjects  

    Note: The Source IP's belong to the User ID: ANONYMOUS_PRINCIPLE, seems like a lead.
    <br />
    <br />


1. Identify Suspicious Source IPs: Determine if there are any suspicious or anomalous access patterns based on source IP addresses:
    ```s
    index="main" source="AWS_S3_HoneyBucketLogs.csv" host="ubuntu"
    | stats count by "Source IP"
    | sort - count
    ```
    Note: There seems to be a high count of Source IP: 212.83.184.15 (ANONYMOUS_PRINCIPLE)  
    
    Note: Unathorized Access: Chat explained that the identifier "ANONYMOUS_PRINCIPLE" typically points to actions attempted by users who are not authenticated. This might indicate eigther unauthenticated public access or, more concerningly, attempts to access your resources without proper credentials.

    Note: Frequent Activity from One Source: The fact that this 'User ID: ANONYMOUS_PRINCIPLE' correlates with the most active 'Source IP' suggests a pattern of behavior that is atypical and potentially malicious. This specific IP might be engaged in probing, scanning, or other forms of attack aimed at exploiting vulnerabilities.
    <br />
    <br />

    
1. User Agent Analysis: Analyze the user agents involved in the requests to identify any patterns indicative of automated tools or scripts:
    ```s
    index="main" source="AWS_S3_HoneyBucketLogs.csv" host="ubuntu"
    | stats count by "Request User Agent"
    | sort - count
    ```
    Note: The output shows the highest count as Go-http-client/1.1 (Go Script) w/ 258/264 events being non-other thank ANONYMOUS_PRINCIPLE.  

    Note: The second highest count is Boto3/1.17.40 Python/3.6.12 Linux/3.10.0-1160.6.1.el7.x86_64 Botocore/1.20.112 and there are 110/110 events showing ANONYMOUS_PRINCIPLE.
    <br />
    <br />

    
1. Alarm and Alert Analysis: Examine any alarms or alerts that have been triggered to identify potential security incidents:
    ```s
    index="main" source="AWS_S3_HoneyBucketLogs.csv" host="ubuntu"
    | stats count by Alert, "Alarm DateTime"
    | sort - count
    ```
    
    Note: I mean every click alerts and times are ANONYMOUS_PRINCIPLE
    <br />
    <br />


1. Temporal Analysis: Check the distribution of events over time to spot any unusual spikes or patterns in activity:
    ```s
    index="main" source="AWS_S3_HoneyBucketLogs.csv" host="ubuntu"
    | timechart span=1h count by "Event Name"
    ```

    Note: Spike in Event Names: HeadBucket, ListObjects from ANONYMOUS_PRINCIPLE at 2024-04-22 15:00 284/301 and 
    2024-04-22 17:00 284/301
    <br />
    <br />









