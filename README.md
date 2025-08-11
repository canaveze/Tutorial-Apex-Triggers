# Apex-Triggers
Apex Triggers Trailhead module tutorial with all codes and step by step

## Get Started with Apex Triggers

### Apex

trigger AccountAddressTrigger on Account (before insert, before update) {
    for(Account a: Trigger.New){
        if(a.Match_Billing_Address__c == true && a.BillingPostalCode!=null){
            a.ShippingPostalCode=a.BillingPostalCode;
        }
    }
}
