# Briebo Reader — Privacy Policy

**Effective date:** November 2, 2026  
**App:** `briebo-reader` (a Reddit Devvit application)  
**Operator:** The independent Briebo Reader project  
**Privacy contact:** [Message the app operator on Reddit](https://www.reddit.com/message/compose/?to=ajcolub)

This policy explains how Briebo Reader handles information when you interact with the app, and distinguishes its existing read-only Reddit viewer from proposed Discord and AI handoff features. **Those optional outbound and AI features are not enabled merely by publishing this policy.** Technical implementation and platform authorization must be verified before activation.

## 1. Information the app accesses

The reader requests public Reddit discussion listings, initially from `r/devvit`, through Reddit's Devvit platform interfaces. The intended displayed data is limited to up to three public post titles with post links and the associated Reddit identifiers needed to retrieve and validate the posts.

Reddit's API responses may include additional public post metadata while the app processes a listing; that does not mean every field is displayed or intentionally retained. The reader is not intended to request private Reddit messages, private account histories, saved posts, passwords or payment information.

Reddit and its hosting infrastructure may separately collect account, usage, device or technical information under Reddit's own policies. This policy governs the independent Briebo Reader project's handling of data, not Reddit's independent processing.

## 2. Purpose and use

The app uses public post information to show recent topics to a reviewer within Reddit. Post titles and linked discussions are **untrusted discussion leads**, not verified factual evidence.

An optional, separately controlled integration is designed to send no more than three public discussion titles, post IDs and permalinks to one **private Discord webhook channel**, along with a retrieval time, a payload version, classification and a SHA-256 digest for transport integrity. That digest is not user authentication or a statement that the discussion is true. The integration is subject to platform-permission review and is not described as currently active.

A further optional feature could present retained discussion leads to Briebo's externally hosted AI-assisted planner. It would use them for topic selection or analysis, **not for model training or fine-tuning**. It is disabled pending separate approval and additional safeguards. The project does not use Reddit data for targeted advertising or sell Reddit data.

## 3. Sharing and recipients

If a future authorized handoff is activated, public discussion data in the payload would be transmitted over HTTPS from Reddit Devvit to Discord and made accessible to people or services with permission to view the specified private Discord channel. Discord would process those messages under its own policies.

If separately authorized AI analysis is later enabled, the selected discussion leads may be sent to the configured AI provider for inference, under that provider's applicable processing terms. Enabling the Discord handoff **alone** does not enable title retention or AI access.

No such external transfer should occur until the necessary permissions and deletion-handling obligations have been assessed. Do not assume that the domain being globally allowlisted by Reddit approves the proposed data use.

## 4. Storage, retention and security

The planned Briebo receiving service uses three independent, default-off configuration gates:

- **Intake only:** With the intake gate explicitly enabled and title retention disabled, it records a limited audit of message state, retrieval/receipt times, payload digest and post count. It does not store the Reddit titles or permalinks in the receiving database. The audit records are designed to expire after **30 days**.
- **Retained titles (not authorized for activation yet):** A separate opt-in gate would retain up to three titles and permalinks for at most **12 hours** in a protected local database. The proposed Devvit Discord message lifetime is up to **24 hours**. These are maximum design windows, not promises of immediate source-deletion detection.
- **AI planner access (not authorized for activation yet):** A third gate would allow eligible, unexpired retained titles to be considered as untrusted leads. Its durable cycle summaries are designed to record counts, not the titles or links.

Operational systems may maintain limited access, error and message-delivery records necessary for debugging and security. Webhook credentials are intended to be held in secret settings, not public code; access to the receiving channel and database is restricted by operator permissions. No security measure is guaranteed to prevent every incident.

## 5. Deletion, edits and withdrawal

The receiving service is designed to clear its local retained titles when it observes expiration, deletion of the **Discord message**, or a substantive Discord edit. It does **not currently establish that deletion or removal of the original Reddit post is propagated to Discord and every downstream retained copy**. This is an unresolved implementation requirement.

**Because that safeguard is incomplete, the planned title-retention and AI-planner gates must remain disabled.** A short retention period, deletion of Discord messages, or the publication of this policy does not cure this gap.

If you authored a Reddit post and have a privacy or deletion concern relating to Briebo Reader, please [contact the operator](https://www.reddit.com/message/compose/?to=ajcolub) with a link or post ID and a description of the request. We will review requests consistent with applicable law, Reddit policies and the data actually under our control. Deleting a Reddit post does not by itself prove every external copy has been deleted; the integration is not to be expanded while this remains unresolved.

## 6. Your choices

You can choose not to interact with the app. Reddit's own controls govern the visibility and deletion of your original Reddit content. For requests about information held by the Briebo Reader operator, use the contact link above. There is no implemented self-service export or automated deletion portal.

The reader does not require a separate Briebo Reader account or ask for your password or payment details.

## 7. Updates to this policy

This policy may be updated when collection, sharing, retention, service providers or permissions change. Material changes should be reflected here **before** activating affected features. The effective date will be revised accordingly.

## 8. Contact and related terms

[Contact the operator on Reddit](https://www.reddit.com/message/compose/?to=ajcolub) for privacy questions.

The app's [Terms and Conditions](BRIEBO-READER-TERMS.md) describe permitted use and service limitations. Reddit's and Discord's own privacy policies govern their separate processing.

---

**Status clarification:** This policy describes existing read-only functionality and planned, disabled integrations. It is not evidence that Reddit authorized external data sharing, hosted-model processing, or that original-post deletion propagation has been implemented.
