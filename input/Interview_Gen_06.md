# Interview: David Kim (Sales Operations Manager)
Date: 2025-10-19
Topic: The Stack and Data Hygiene

**Interviewer:**  David, hey. Thanks for letting me into the server room, metaphorically speaking. How are the databases behaving today?

**David:**  "Behaving"? That implies they have manners. They're feral. I've been fighting fires all morning. The API sync broke again at 3 AM. Woke me up.

**Interviewer:**  Yikes. Sorry to hear that. So, you manage the CRM and the whole tech stack. Besides the 3 AM wake-up calls, what’s the biggest operational headache you deal with?

**David:**  Data integrity. 100%. No doubt about it. Our CRM is a graveyard. It's a graveyard of outdated info. Reps enter stuff manually, and they make mistakes. Fat fingers, lazy entries, or they just don't enter it at all. It's Swiss cheese.

**Interviewer:**  Why is it so hard to keep clean? We have tools for this, right?

**David:**  You'd think. But the problem is that the source of truth isn't the CRM anymore. It’s the internet. Specifically, it's LinkedIn. People assume LinkedIn profiles are the gold standard. So a rep finds a prospect, sees they have a new title on LinkedIn, and maybe they update Salesforce, maybe they don't. Usually they don't. We have tools—ZoomInfo, Clearbit—that are supposed to sync this auto-magically, but they break, or they’re too expensive to run on every single contact record. So we rely on humans.

**Interviewer:**  So the sales reps are the bridge between the internet and your database?

**David:**  Unfortunately. And they hate it. They despise it. They call it "admin time" or "overhead". They claim they spend 2 hours a day just updating contact fields based on what they see online. "Oh, this company was acquired," or "This guy was promoted to VP." It’s all public info! It's right there! Why do I have a human being paid $80k a year acting as a copy-paste machine? It makes no sense.

**Interviewer:**  Is there a lot of variety in where they find this info? Or is it all just one place?

**David:**  They say there is. They tell me, "Oh I checked Crunchbase, I checked the news, I checked the stock ticker." But I see the web traffic logs. I know the truth. It’s 90% LinkedIn. They just keep that tab open all day. It’s their real database. Ours is just where they log the result so they get paid commissions. It's backwards.
