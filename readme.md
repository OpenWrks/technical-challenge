For current open positions, see <https://openwrks.bamboohr.com/jobs/>

---

<img src="https://www.openwrks.com/assets/img/openwrks-logo_black.svg" width="400">

# OpenWrks Technical Challenge

## About Our Challenge

- ⏳ We respect your time, and expect that you'll have to make choices and tradeoffs for what's in scope for your chosen option
- 🛠 We're looking for a solution that's well designed, intuitive and tested
- 🧰 You can use any language and tooling of your choice. Our only requirement is that your solution must be runnable on another computer
- 💾 Your solution must be available for us to pull from a public or privately hosted repository
- 📥 The technical challenge must be submitted to us by mid-day the working day before your technical interview

### Option 1 - Build a Netflix Review Service 🛠

We'd like to see you build a Netflix Review Service API that has the following functionality:

- **Get shows**

  - Shows are available via an API
  - Review ratings and descriptions (where they have been submitted) are returned alongside the show information

- **Submit a review**
  - A review can be submitted via an API
  - A review must contain a rating and a description:
    - The review rating is out of 5
    - The review description must not be empty but must be smaller than 256 characters

We've provided two APIs to allow you to get Netflix show data:

1. **(OpenWrks) Netflix API**

   - URL: https://netflix-app.openwrks.com

   - API Docs: https://netflix-app.openwrks.com/swagger

   This API returns paginated Netflix show data that you should base your Review Service on. The API schema is described in the documentation (Swagger) linked above.

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

   Using cURL (Authorization header base64 encoded)

   ```bash
   curl -X POST "https://netflix-auth.openwrks.com/connect/token" \
   -H "Authorization: Basic YXBwbGljYW50OmcqOGdkdzI0WFg0NWdzYXdmRERjc3phQGU=" \
   -H "Content-Type: application/x-www-form-urlencoded" \
   --data-urlencode "grant_type=client_credentials" \
   --data-urlencode "scope=netflix.shows.read"
   ```

   Using [VS Code’s REST Client extension](https://marketplace.visualstudio.com/items?itemName=humao.rest-client) (by Huachao Mao)
   (VS Code's REST client will base64 encode the Authorization header on your behalf)

   ```http
   POST https://netflix-auth.openwrks.com/connect/token
   content-type: application/x-www-form-urlencoded
   authorization: Basic applicant:g*8gdw24XX45gsawfDDcsza@e
   grant_type=client_credentials&scope=netflix.shows.read
   ``

   ```

❗ **NOTE:** While our Netflix API will provide you with show data, it will not provide you with review data or allow you to submit reviews. This is a feature your API will need to support.

### Option 2 - Show off something you’ve built before 👁️‍🗨️

Whether it's an open-source contribution, side project, or something else you’re proud of, we’d love you to talk us through it.

When choosing this option, please make sure that it shows you off to the best of your ability and fits the criteria we're looking for. We want to see something that's well designed, intuitive, and tested.

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

If you do get stuck or have any questions, please get in touch in the Slack group we have invited you to 😄
