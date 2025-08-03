# Security Policy

Knowledge Center Logo
Search
Home
Unity LevelPlay Platform
Unity LevelPlay SDK
ironSource Ads monetization
ironSource Ads user acquisition
My account
News and updates
Contact us
Contact us
Home/
Unity LevelPlay Platform/
Segments best practices
Segments best practices
Proper user segmentation is a valuable component of any successful in-app monetization strategy. There is no one-size-fits-all approach to segmentation, so you want to make sure your ad strategy is as diverse as your users. With Unity LevelPlay’s segments tool, you can tailor your users’ ad experiences based on a vast number of conditions, as well as continually analyze and test unique strategies for a compelling user experience.  

Regardless of how simple or complex your segmentations are, these are the best practices you should follow to maximize your application’s potential:

Decide how you want users to experience your application  Before setting any segments, analyzing KPIs, or optimizing your strategy, think creatively about how you believe users should engage with ads in your application, and how that experience may impact other parts of the app. Think holistically and individually. How should ads be applied in general, and how do you want to diversify the ad experience based on your preferences? Once you decide, continue to be curious and perfect your strategy over time.  
Understand your audience personae  Every app, genre, and country, has unique users with unique characteristics. Understand who your audience is, and tailor your approach accordingly. For example, users past level 10 may be willing to watch more rewarded videos at a lesser value per view, so you may want to adjust capping rules and reward amounts for this segment.    
Evaluate performance on an application level and segment level  It’s important to understand how each unique segment is contributing to an application’s overall performance. Use the Performance and User Activity reports in your ironSource account to measure the impact on revenue and user engagement KPIs for each segment independently. For example, if you have one segment with a relatively low engagement rate (% of DAU engaging with an ad unit) but a high ARPDEU (average revenue per daily engaged user), you would use this level of data granularity to focus your optimization efforts on the segment’s engagement rate to maximize revenue.
A/B test your segments  When deciding how to segment your users, A/B test your strategy before applying any changes to your full audience. ironSource’s A/B testing module lets you try out different segment settings and get valuable insights on whether those changes boost ARPDAU and retention. We recommend testing the following segments:
Payer vs. Non-payer reward amount
IDFA vs IDFV waterfall optimization 
Increase or decrease capping and pacing rules in high-traffic geos
Exponential rewards (increasing reward amount as user progresses) 
Adjusting ad behavior for the first-time user experience (FTUE)
Rank your segments  When multiple segments are defined, it’s possible that users will fall into more than one segment. Prioritize your segments by level of importance, which can be decided based on revenue KPIs, retention goals, or game-flow design elements. 
 Combine placements and mediation groups with your segments  Segmentation does not have to be applied across an entire application. There may be situations that call for an adjustment to the ad behavior of one placement for a segment, while maintaining the ad behavior of another placement for the same segment. For example, you could decide to turn off a rewarded video ad placement that rewards your application’s main purchase currency for players that have already spent money on in-app purchases.
segment

Also, the example where users past level 10 may be willing to watch more rewarded videos at a lesser value per view may only apply in particular countries. In that case, you should only apply this segment rule to a particular mediation group: 

User segment example

Learn more about best practices for placements here.

import java.security.*;
import java.math.BigInteger;
public class HelloWorld {
     public static void main(String []args) {
        
        validateSuperSonicCallback();
     }
     
    public static String getPostParameter(String param){
         // TODO : your app implementaion for get post parmas
        return "";
     }
	 
	  public static boolean alreadyProcessed(String eventId){
         // TODO 
        return true;
     }
     public static boolean validateSuperSonicCallback() {
         
         String applicationUserId = getPostParameter("applicationUserId");
         String eventId = getPostParameter("eventId");
         String signature = getPostParameter("signature");
         String userId = getPostParameter("userId");
         String rewards = getPostParameter("rewards");
         String timestamp = getPostParameter("timestamp");
         String privateKey = "myPrivateKey" ;// enter your private key
         String mySignature = "";
        try {
            String message = timestamp + eventId + userId + rewards +privateKey;
            MessageDigest md = MessageDigest.getInstance("MD5"); 
            md.update(message.getBytes());
            BigInteger hash = new BigInteger(1, md.digest());
            String result = hash.toString(16);
            while(result.length() < 32) {
                result = "0" + result;
            }
                        System.out.println(result); // Display the string.
        } catch (NoSuchAlgorithmException e){
        }
        if (mySignature!=signature){
	     return false;
	}else{
	     return !alreadyProcessed(eventId);
    }
     
  }
}
## Supported Versions

Use this section to ![73874328-64a8-463e-b0f1-a906a51ceff5-1_all_77](https://github.com/user-attachments/assets/5c1d5b7f-7683-44fc-aaf4-e353acffba0a)
<img width="1086" height="435" alt="73874328-64a8-463e-b0f1-a906a51ceff5-1_all_69" src="https://github.com/user-attachments/assets/3092cb6a-d1e4-4f5b-90ce-cd398e43fa1b" />
tell people about which versions of your project are
currently being supported with security updates.

| Version | Supported          |
| ------- | ------------------ |
| 5.1.x   | :white_check_mark: |
| 5.0.x   | :x:                |
| 4.0.x   | :white_check_mark: |
| < 4.0   | :x:                |

## Reporting a Vulnerability

U// get the variables
$userId = $_GET['applicationUserId'];
$eventId = $_GET['eventId'];
$rewards = $_GET['rewards'];
$signature = $_GET['signature'];
$timestamp = $_GET['timestamp'];
$privateKey = ‘[YOUR_PRIVATE_KEY]’;
// validate the call using the signature
if (md5($timestamp.$eventId.$userId.$rewards.$privateKey) != $signature)
{
   echo "Signature doesn’t match parameters";
   return;
}
// check that we haven't processed the same event before
if (!alreadyProcessed($eventId)){
   // grant the rewards
   doProcessEvent($eventId, $userId, $rewards);
}
// return ok
echo $eventId.":OK";https://saas-java-971.my.salesforce.com/se this section to tell people how to report a vulnerability.

Tell them where to go, how often they can expect to get an update on a
reported vulnerability, what to expect if the vulnerability is accepted or
declined, etc.// get the variables
$userId = $_GET['applicationUserId'];
$eventId = $_GET['eventId'];
$rewards = $_GET['rewards'];
$signature = $_GET['signature'];
$timestamp = $_GET['timestamp'];
$privateKey = ‘[YOUR_PRIVATE_KEY]’;
// validate the call using the signature
if (md5($timestamp.$eventId.$userId.$rewards.$privateKey) != $signature)
{
   echo "Signature doesn’t match parameters";
   return;
}
// check that we haven't processed the same event before
if (!alreadyProcessed($eventId)){
   // grant the rewards
   doProcessEvent($eventId, $userId, $rewards);
}
// return ok
echo $eventId.":OK";
