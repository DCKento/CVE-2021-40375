# CVE-2021-40375 - Broken Access Control in OpenEyes 3.5.1

## Description

An improper access control vulnerability was identified in OpenEyes 3.5.1, developed by the Apperta Foundation.

A low privileged user could load a patient's profile in their browser and access sensitive information without the required level of privilege. Despite the application returning a 'Forbidden' message on the webpage, the server response still returned all the information about a patient. This information could be viewed in an intercepting proxy, or simply by viewing the page source within the browser.

## Reproduction
1. As a highly privileged user, view a patient profile.
2. Copy the URL to this patient profile.
3. Log out of the OpenEyes session.
4. Log in with a low privileged user.
5. Paste the patient profile URL in and browse to this.
6. Note that OpenEyes returns a 'Foribidden' message.
7. Right click and click 'View page source'.
8. Note that the sensitive patient information is still returned in the response, and can be viewed in the page source.

## Impact

The patient overview contains sensitive information about the patient. This includes PII such as Date of Birth, NHS number and address. In addition, extensive medical information is disclosed such as medication plans, prescription informations, past appointments, current medical problems or past procdeures.

This information being obtained by a user who is unauthorized could result in a breache of privacy, and impact the confidentiality of patient information stored within the OpenEyes application.

## Demonstration



https://user-images.githubusercontent.com/20635370/131623408-96ea48aa-68b8-4b71-8f00-8da9c9555ed5.mp4


