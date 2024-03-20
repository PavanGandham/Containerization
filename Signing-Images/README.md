# Signing Container Images

This repository provides instructions for signing container images following the guidelines provided in the Snyk blog post: [Signing Container Images](https://snyk.io/blog/signing-container-images/).

## Prerequisites

Before you begin, ensure you have the following prerequisites installed and configured:

- Docker: [Installation Guide](https://docs.docker.com/get-docker/)
- GPG (GNU Privacy Guard): [Installation Guide](https://gnupg.org/download/index.html)
- Snyk Account: [Sign up here](https://snyk.io/login)

## Steps to Sign Container Images

Follow these steps to sign container images using GPG and Snyk:

1. **Generate GPG Key Pair**: If you haven't already, generate a GPG key pair using the `gpg --gen-key` command. Follow the prompts to complete the key generation process.

2. **Export Public Key**: Export the public key to share with others. Use the `gpg --export --armor <your_email>` command to export the public key in ASCII armor format.

3. **Sign Container Image**: Sign your container image using the GPG key. The following command demonstrates signing a Docker image:
   ```bash
   docker trust sign <your_image>
   ```

4. **Push Signed Image to Registry**: Push the signed image to your desired container registry. Ensure you have proper authentication to push the image.

5. **Verify Signature**: After pushing the signed image, you can verify the signature using the `docker trust inspect --pretty <your_image>` command.

6. **Integrate with Snyk**: Sign up or log in to your Snyk account. Follow the Snyk documentation to integrate image signing with Snyk Container: [Snyk Container Image Signing](https://docs.snyk.io/snyk-container/image-signing/).

## Additional Resources

- [Snyk Blog: Signing Container Images](https://snyk.io/blog/signing-container-images/)
- [Docker Documentation](https://docs.docker.com/)
- [GPG Documentation](https://gnupg.org/documentation/)

