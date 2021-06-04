For current open positions, see <https://openwrks.bamboohr.com/jobs/>

------------------

<img src="https://www.openwrks.com/assets/img/openwrks-logo_black.svg" width="400">

# OpenWrks Technical Challenge

## About Our Challenge

- ⏳ ~ We respect your time, and expect that you will have to make choices and tradeoffs for what is in scope for your chosen option.
- 🛠 ~ If you want to impress us then we want to see a solution that is well designed, intuitive and tested.
- 🧰 ~ You can use any language and tooling of your choice that your are most productive with. Our only requirements here is that your solution must be runnable on another computer.
- 💾 ~ Your solution must be available for us to pull from a public or privately hosted repository.

### Option 1 - Build a Netflix Review Service 🛠

We would like to see you build a Netflix Review Service API that has the following functionality:

- **Get shows**

  - Shows are available via API
  - Review ratings and descriptions (where they have been submitted) are returned with the show information

- **Submit a review**
  - A review can be submitted via API
  - A review must contain a rating and a description
    - The review rating is out of 5
    - The review description must not be empty but must be smaller than 256 characters

We have provided two APIs to allow you to get Netflix show data:

1. **(OpenWrks) Netflix API**

   - URL: https://netflix-app.openwrks.com

   - API Docs: https://netflix-app.openwrks.com/swagger

   This API returns Netflix show data that you should base your Review Service on. The API schema is described in the API documentation, linked above.

   To access the API, your application will need to obtain a short-lived JSON Web Token (JWT) from the Netflix Auth Service, as described below.

2. **(OpenWrks) Netflix Auth Service**

   - URL: https://netflix-auth.openwrks.com

   This API is (loosely) based on the OAuth2 specification and provides the ability to get a token to access the Netflix App, via the client credentials flow.

   **Credentials**

   - client_id: applicant
   - client_secret: g\*8gdw24XX45gsawfDDcsza@e
   - grant_type: client_credentials
   - scope: netflix.shows.read

   **Sample Requests**

   Using cURL

   ```bash
   curl -X POST "https://netflix-auth.openwrks.com/connect/token" \
   -H "Authorization: Basic YXBwbGljYW50OmcqOGdkdzI0WFg0NWdzYXdmRERjc3phQGU=" \
   -H "Content-Type: application/x-www-form-urlencoded" \
   --data-urlencode "grant_type=client_credentials" \
   --data-urlencode "scope=netflix.shows.read"
   ```

   Using [VS Code’s REST Client extension](https://marketplace.visualstudio.com/items?itemName=humao.rest-client) (by Huachao Mao)

   ```http
   POST https://netflix-auth.openwrks.com/connect/token
   content-type: application/x-www-form-urlencoded
   authorization: Basic applicant:g*8gdw24XX45gsawfDDcsza@e
   grant_type=client_credentials&scope=netflix.shows.read
   ```

### Option 2 - Show off something you’ve built before 👁️‍🗨️

Whether it is an open-source contribution, side project, or something else you’re proud of; we’d love you to talk us through it.

When choosing this option, please make sure that it shows off you to the best of your ability and also shows enough of your ability (something that is well designed, intuitive and tested).

## Next Steps

Once you’ve completed and submitted your solution, we’ll schedule a video call to discuss what you’ve done.

This will include:

- Demoing it
- Discussing any tests you’ve written (and any that we think would be good additions)
- Discussing infrastructure
- Discussing how your solution could scale (it doesn’t need to be perfect today but it’d be great to hear your ideas)
- Discussing how we could make it production-ready
- System monitoring and observability

## Need Help?

If you do get stuck or have any questions, please get in touch in the Slack group we have invited you to :)
