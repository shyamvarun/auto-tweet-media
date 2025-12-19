Media Upload Failure – 403 Forbidden (Free Tier Limitation)

This repository contains workflow files and Python scripts intended to upload media to X (formerly Twitter) using the Tweepy library. Authentication has been configured correctly, and the application is authorised with Read and Write permissions.

During the execution of the GitHub Actions workflow, the media upload process fails with a “tweepy.errors.Forbidden: 403 Forbidden” message, resulting in the workflow ending with exit code 1. The traceback confirms that the error occurs when the script attempts to run the command “media = api.media_upload(image)”. This indicates that authentication with X services is functioning properly, but the platform is rejecting the media upload request.

The issue has been identified as a limitation of the free tier provided by the X Developer Platform. The platform restricts access to various API endpoints based on subscription level. Free tier access offers only limited support for the v1.1 API endpoints, and media upload capability is not guaranteed at this level. As a result, any attempt to upload media using this tier may lead to a 403 Forbidden error.

At present, authentication and text-related operations may continue to work; however, media upload functionality is not supported under the current subscription tier. To resolve this issue, it is necessary to upgrade the X Developer subscription to a higher plan that supports media upload features. Alternatively, text-only posting may continue to be used if access remains on the free tier.

This repository is maintained for experimental and educational use. Media upload failures should be expected until the account is upgraded to a subscription level that supports this functionality.
