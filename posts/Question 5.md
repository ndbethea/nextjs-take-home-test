---
title: '5. A customer writes in to our GitHub community stating "I have a custom domain
which I purchased at GoDaddy and I want to use it on my project". In a couple of
paragraphs, how do you respond?'
date: '2022-04-22'
---

Hello, fortunately for you Vercel does offer a way to do that. Using the Vercel API you are able to add custom domains to your Vercel accounts. How you accomplish that is by sending a POST request to this endpoint: https://api.vercel.com/v4/domains. After doing that, in order for you to test a POST request to this endpoint, you are able to use the curl command in your terminal. Lastly, you will also need to add a testing token inside your POST request.

Below are example requests for adding a domain to a Vercel personal account, and team account.

**For Personal Account**

curl -X POST "https://api.vercel.com/v4/domains" \
  -H "Authorization: Bearer TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
  "name": "example.com"
}'
Adding example.com to your Vercel personal account.

**For Team Account**

You will first need to obtain the team ID using a GET request to this endpoint: https://api.vercel.com/v1/teams. Then, 

curl "https://api.vercel.com/v1/teams" \
  -H "Authorization: Bearer TOKEN"
Listing all the teams associated with your Vercel personal account.

Here is an example request for adding a domain to a Vercel team account.

curl -X POST "https://api.vercel.com/v4/domains?teamId=TEAM_ID" \
  -H "Authorization: Bearer TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
  "name": "example.com"
}'
Adding example.com to a Vercel team account.

NOTE: Make sure to completely replace TOKEN and TEAM_ID with their respective token and ID before making a Vercel API request.

[Click here to learn more](https://vercel.com/support/articles/how-do-i-add-a-domain-using-the-vercel-api), and hopefully this solves your issue.