# Spam
Most of us are pretty familiar with spam.It seems to clog up our inboxes on your email, that is not the only place that you might receive **an unsolicited message that we would refer to as Spam.** You could be reading online forums, for example and see unsolicited messages that are posted there as well.

**If you receive spam over instant messaging or over text messaging then that is referred to as SPIM (Spam Over Instant Messaging).**

---
#### Content of spams could be:
The content within a spam message can take many different forms. Often it is a commercial message where somebody is trying to sell you a product and they're sending you this unsolicited message as advertisement.
You might also receive spam as a non-commercial message. This might be an organization or an individual that's trying to promote a particular world view.
And of course there is a spam that is malicious, that is trying to phish you for information and gather personal information from you by using these spam messages.
in summary:
> Various content
>  - Commercial advertising
>  - Non-commercial proselytizing 
>  - Phishing attempts
 
 ---
 ### Mail Gateways
 There are many different strategies for blocking spam and preventing it from getting into our mailboxes. One strategy is to have your own spam filter that is either filtering in the cloud or perhaps filtering on site on your own screened subnet. There will be a mail gateway. Your mail comes from internet is filtered in that mail gateway and anything identified as spam can be thrown out before it is transferred into your internal mail server.
 
 The email gateway or spam filter is looking at these messages for particular characteristics. One of these might be an allowed list so that only email from trusted senders is allowed in.
 
 The people who are sending the spam message to you don't always comply with the standards associated with email transfer. So one of the things that your spam filter can do is identify when these messages are not compliant with the RFCs and throw out any messages that seem to go outside the scope of the standards.
 
 Another great test is to perform reverse DNS. You'll receive a message, perhaps from someone that says "unknown.com", Your spam filter will then perform a reverse DNS, look at the IP address associated with "unknown.com" and make sure that the email they received is one that came from this known IP address. If it came from a different IP address your spam filter can mark that as something that is suspicious and prevent that from going to your users.
 
 Another Technique that frustrates these spam senders is one called **Tarpitting**. They want to be able to send this spam to as man people as possible as quickly as possible and what trapitting does is slow down your mail server and make the process of sending and receiving the messages back and forth take an excessive amount of time. The slowing down of the conversation also slow down the spammer's email server. So they may choose to simply skip over you and go on to another user that doesn't slow down the conversation.
 
  And lastly there is Recipient filtering. Very often the spammers will send messages into nay particular name they can find even if that name doesn't actually exist in your organization and many organization will have a catch all where all of those messages are kept. 
  
  **There is never any single strategy for stopping spam. You have to use many different techniques and strategies to make sure that you can stop this before it arrives in your users's inboxes.**

