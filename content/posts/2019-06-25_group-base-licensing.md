---
title: Group based licensing - a new business model for Microsoft?
date: 2019-06-25
draft: false
---

Lets face it. Microsoft 365 implementation projects can get a bit messy. You start exploring possibilities, you create Azure AD groups, you sync some from Active Directory and you assign policies in Intune. Then you might want to install features for pilot users before you configure the policy for all users.

Well what about group based licensing? Are you shoveling money into Microsofts pockets if you lose your firm grip over groups that have licences assigned? 

I was asked this question today, and honestly, I could come up with reasons in any direction. 

Well that called for some testing. 

So in my trial tenant I created two groups:
- E5_one
- E5_two

Both were assigned Microsoft 365 E5 licences. 

Then I made john.doe@trial.onmicrosoft.com a member in both groups. 

And lo and behold - the sum of licences was only one licence lower than before. Uff, lucky us. Housekeeping stays a operational obligation not a economical necessity. 