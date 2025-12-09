::: {#contents .section .contents}
## Contents

[About this report](#about-this-report)

1.  [Report parameters](#report-parameters)

[Summaries](#summaries)

1.  [Alert counts by risk and confidence](#risk-confidence-counts)
2.  [Alert counts by site and risk](#site-risk-counts)
3.  [Alert counts by alert type](#alert-type-counts)

[Alerts](#alerts)

1.  [Risk=[Medium]{.risk-level}, Confidence=[Medium]{.confidence-level}
    (1)](#alerts--risk-2-confidence-2)

[Appendix](#appendix)

1.  [Alert types](#alert-types)
:::

::::: {#about-this-report .section .about-this-report}
## About this report

:::: {#report-parameters .section}
### Report parameters

::: report-parameters--container
#### Contexts

No contexts were selected, so all contexts were included by default.

#### Sites

The following sites were included:

- [http://localhost:8000]{.site}

(If no sites were selected, all sites were included by default.)

An included site must also be within one of the included contexts for
its data to be included in the report.

#### Risk levels

Included: [[High]{.risk-level}, [Medium]{.risk-level},
[Low]{.risk-level}, [Informational]{.risk-level}]{.included-risk-codes}

Excluded: None

#### Confidence levels

Included: [[User Confirmed]{.confidence-level},
[High]{.confidence-level}, [Medium]{.confidence-level},
[Low]{.confidence-level}]{.included-confidence-codes}

Excluded: [ [User Confirmed]{.confidence-level},
[High]{.confidence-level}, [Medium]{.confidence-level},
[Low]{.confidence-level}, [False
Positive]{.confidence-level}]{.included-confidence-codes}
:::
::::
:::::

::: section
:::

:::::: {#summaries .section .summaries}
## Summaries

::: {#risk-confidence-counts .section}
### Alert counts by risk and confidence

+----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
|                      | Confidence                                                                                                                                                                                                     |
|                      +----------------------------------------+----------------------------------------+------------------------------------------+----------------------------------------+------------------------------------------+
|                      | User Confirmed                         | High                                   | Medium                                   | Low                                    | Total                                    |
+======+===============+========================================+========================================+==========================================+========================================+==========================================+
| Risk | High          | 0\                                     | 0\                                     | 0\                                       | 0\                                     | 0\                                       |
|      |               | [(0.0%)]{.additional-info-percentages} | [(0.0%)]{.additional-info-percentages} | [(0.0%)]{.additional-info-percentages}   | [(0.0%)]{.additional-info-percentages} | [(0.0%)]{.additional-info-percentages}   |
|      +---------------+----------------------------------------+----------------------------------------+------------------------------------------+----------------------------------------+------------------------------------------+
|      | Medium        | 0\                                     | 0\                                     | 1\                                       | 0\                                     | 1\                                       |
|      |               | [(0.0%)]{.additional-info-percentages} | [(0.0%)]{.additional-info-percentages} | [(100.0%)]{.additional-info-percentages} | [(0.0%)]{.additional-info-percentages} | [(100.0%)]{.additional-info-percentages} |
|      +---------------+----------------------------------------+----------------------------------------+------------------------------------------+----------------------------------------+------------------------------------------+
|      | Low           | 0\                                     | 0\                                     | 0\                                       | 0\                                     | 0\                                       |
|      |               | [(0.0%)]{.additional-info-percentages} | [(0.0%)]{.additional-info-percentages} | [(0.0%)]{.additional-info-percentages}   | [(0.0%)]{.additional-info-percentages} | [(0.0%)]{.additional-info-percentages}   |
|      +---------------+----------------------------------------+----------------------------------------+------------------------------------------+----------------------------------------+------------------------------------------+
|      | Informational | 0\                                     | 0\                                     | 0\                                       | 0\                                     | 0\                                       |
|      |               | [(0.0%)]{.additional-info-percentages} | [(0.0%)]{.additional-info-percentages} | [(0.0%)]{.additional-info-percentages}   | [(0.0%)]{.additional-info-percentages} | [(0.0%)]{.additional-info-percentages}   |
|      +---------------+----------------------------------------+----------------------------------------+------------------------------------------+----------------------------------------+------------------------------------------+
|      | Total         | 0\                                     | 0\                                     | 1\                                       | 0\                                     | 1\                                       |
|      |               | [(0.0%)]{.additional-info-percentages} | [(0.0%)]{.additional-info-percentages} | [(100.0%)]{.additional-info-percentages} | [(0.0%)]{.additional-info-percentages} | [(100%)]{.additional-info-percentages}   |
+------+---------------+----------------------------------------+----------------------------------------+------------------------------------------+----------------------------------------+------------------------------------------+

: This table shows the number of alerts for each level of risk and
confidence included in the report.\
(The percentages in brackets represent the count as a percentage of the
total number of alerts included in the report, rounded to one decimal
place.) {.risk-confidence-counts-table}
:::

::: {#site-risk-counts .section}
### Alert counts by site and risk

+------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
|                              | Risk                                                                                                                                                                |
|                              +--------------------------------------+----------------------------------------+-------------------------------------+-----------------------------------------------+
|                              | High\                                | Medium\                                | Low\                                | Informational\                                |
|                              | [(=                                  | [(\>=                                  | [(\>=                               | [(\>=                                         |
|                              | High)]{.additional-info-percentages} | Medium)]{.additional-info-percentages} | Low)]{.additional-info-percentages} | Informational)]{.additional-info-percentages} |
+======+=======================+======================================+========================================+=====================================+===============================================+
| Site | http://localhost:8000 | 0\                                   | 1\                                     | 0\                                  | 0\                                            |
|      |                       | [(0)]{.additional-info-percentages}  | [(1)]{.additional-info-percentages}    | [(1)]{.additional-info-percentages} | [(1)]{.additional-info-percentages}           |
+------+-----------------------+--------------------------------------+----------------------------------------+-------------------------------------+-----------------------------------------------+

: This table shows, for each site for which one or more alerts were
raised, the number of alerts raised at each risk level.\
Alerts with a confidence level of \"False Positive\" have been excluded
from these counts.\
(The numbers in brackets are the number of alerts raised for the site at
or above that risk level.) {.site-risk-counts-table}
:::

::: {#alert-type-counts .section}
### Alert counts by alert type

  -------------------------------------------------------------------------------------------
  Alert type               Risk                    Count
  ------------------------ ----------------------- ------------------------------------------
  [Missing                 Medium                  2\
  Anti-clickjacking                                [(200.0%)]{.additional-info-percentages}
  Header](#alert-type-0)                           

  Total                                            1
  -------------------------------------------------------------------------------------------

  : This table shows the number of alerts of each alert type, together
  with the alert type\'s risk level.\
  (The percentages in brackets represent each count as a percentage,
  rounded to one decimal place, of the total number of alerts included
  in this report.) {.alert-type-counts-table}
:::
::::::

::: {#alerts .section .alerts}
## Alerts

1.  ::: {#alerts--risk-2-confidence-2}
    ### Risk=[Medium]{.risk-level}, Confidence=[Medium]{.confidence-level} (1)

    1.  #### [http://localhost:8000]{.site} (1)

        1.  ##### [Missing Anti-clickjacking Header](#alert-type-0) (1)

            1.  [GET http://localhost:8000/]{.request-method-n-url}
                +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
                | Alert tags                        | - [OWASP_2021_A05](https://owasp.org/Top10/A05_2021-Security_Misconfiguration/)                                                                                                                          |
                |                                   | - POLICY_QA_STD =                                                                                                                                                                                        |
                |                                   | - POLICY_PENTEST =                                                                                                                                                                                       |
                |                                   | - [CWE-1021](https://cwe.mitre.org/data/definitions/1021.html)                                                                                                                                           |
                |                                   | - [SYSTEMIC](https://www.zaproxy.org/docs/desktop/addons/common-library/alerttags/#systemic)                                                                                                             |
                |                                   | - [WSTG-v42-CLNT-09](https://owasp.org/www-project-web-security-testing-guide/v42/4-Web_Application_Security_Testing/11-Client-side_Testing/09-Testing_for_Clickjacking)                                 |
                |                                   | - [OWASP_2017_A06](https://owasp.org/www-project-top-ten/2017/A6_2017-Security_Misconfiguration.html)                                                                                                    |
                +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
                | Alert description                 | The response does not protect against \'ClickJacking\' attacks. It should include either Content-Security-Policy with \'frame-ancestors\' directive or X-Frame-Options.                                  |
                +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
                | Request                           | Request line and header section (270 bytes)                                                                                                                                                              |
                |                                   |     GET http://localhost:8000/ HTTP/1.1                                                                                                                                                                  |
                |                                   |     host: localhost:8000                                                                                                                                                                                 |
                |                                   |     user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.0.0 Safari/537.36                                                                          |
                |                                   |     pragma: no-cache                                                                                                                                                                                     |
                |                                   |     cache-control: no-cache                                                                                                                                                                              |
                |                                   |     referer: http://localhost:8000/register                                                                                                                                                              |
                |                                   |                                                                                                                                                                                                          |
                |                                   | Request body (0 bytes)                                                                                                                                                                                   |
                +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
                | Response                          | Status line and header section (141 bytes)                                                                                                                                                               |
                |                                   |     HTTP/1.1 200 OK                                                                                                                                                                                      |
                |                                   |     content-type: text/html; charset=UTF-8                                                                                                                                                               |
                |                                   |     vary: Accept-Encoding                                                                                                                                                                                |
                |                                   |     content-length: 3341                                                                                                                                                                                 |
                |                                   |     date: Thu, 27 Nov 2025 14:59:41 GMT                                                                                                                                                                  |
                |                                   |                                                                                                                                                                                                          |
                |                                   | Response body (3341 bytes)                                                                                                                                                                               |
                |                                   |     <!DOCTYPE html>                                                                                                                                                                                      |
                |                                   |     <html lang="en">                                                                                                                                                                                     |
                |                                   |     <head>                                                                                                                                                                                               |
                |                                   |         <meta charset="UTF-8">                                                                                                                                                                           |
                |                                   |         <meta name="viewport" content="width=device-width, initial-scale=1.0">                                                                                                                           |
                |                                   |         <title>Booking System</title>                                                                                                                                                                    |
                |                                   |         <link href="/static/tailwind.css" rel="stylesheet">                                                                                                                                              |
                |                                   |     </head>                                                                                                                                                                                              |
                |                                   |     <body class="flex flex-col min-h-screen bg-gray-100 text-gray-900">                                                                                                                                  |
                |                                   |         <!-- Header -->                                                                                                                                                                                  |
                |                                   |         <div class="container mx-auto p-4 mt-4 text-center">                                                                                                                                             |
                |                                   |             <div class="flex flex-col md:flex-row justify-between space-y-6 md:space-y-0 md:space-x-6 max-w-5xl mx-auto">                                                                                |
                |                                   |                 <!-- Left box -->                                                                                                                                                                        |
                |                                   |                 <div class="bg-white shadow-md rounded-lg p-6 w-full md:w-2/3">                                                                                                                          |
                |                                   |                     <h1 class="text-2xl font-bold mb-4">Welcome to the Booking system</h1>                                                                                                               |
                |                                   |                     <p class="mb-4">Please choose one of the options below:</p>                                                                                                                          |
                |                                   |                     <div id="action-links" class="flex justify-between space-x-4">                                                                                                                       |
                |                                   |                         <a id="add-resource" href="/resources" class="inline-block bg-gray-400 text-white py-2 px-4 rounded w-1/2 cursor-not-allowed pointer-events-none">Add a new resource</a>         |
                |                                   |                         <a id="add-reservation" href="/reservation" class="inline-block bg-gray-400 text-white py-2 px-4 rounded w-1/2 cursor-not-allowed pointer-events-none">Add a new reservation</a> |
                |                                   |                     </div>                                                                                                                                                                               |
                |                                   |                 </div>                                                                                                                                                                                   |
                |                                   |                                                                                                                                                                                                          |
                |                                   |                 <!-- Right box -->                                                                                                                                                                       |
                |                                   |                 <div id="userBox" class="bg-white shadow-md rounded-lg p-6 w-full md:w-1/3">                                                                                                             |
                |                                   |                     <h2 class="text-xl font-bold mb-4">You are not logged in</h2>                                                                                                                        |
                |                                   |                     <p class="mb-4">You must first log in or register.</p>                                                                                                                               |
                |                                   |                     <div id="action-links" class="flex justify-between space-x-4 mt-4">                                                                                                                  |
                |                                   |                         <a href="/login" class="inline-block bg-blue-500 text-white py-2 px-4 rounded hover:bg-blue-600 w-1/2 cursor-not-allowed pointer-events-none">Login</a>                          |
                |                                   |                         <a href="/register" class="inline-block bg-gray-500 text-white py-2 px-4 rounded hover:bg-gray-600 w-1/2">Register</a>                                                           |
                |                                   |                     </div>                                                                                                                                                                               |
                |                                   |                 </div>                                                                                                                                                                                   |
                |                                   |             </div>                                                                                                                                                                                       |
                |                                   |         </div>                                                                                                                                                                                           |
                |                                   |         <main class="flex-grow">                                                                                                                                                                         |
                |                                   |         <!-- Reservations -->                                                                                                                                                                            |
                |                                   |         <div class="container mx-auto p-4 text-center">                                                                                                                                                  |
                |                                   |             <div class="bg-white shadow-md rounded-lg p-6 mb-6 max-w-5xl mx-auto">                                                                                                                       |
                |                                   |                 <h1 class="text-2xl font-bold mb-4">Booked resources</h1>                                                                                                                                |
                |                                   |                 <div class="overflow-x-auto">                                                                                                                                                            |
                |                                   |                     <table class="min-w-full bg-white border border-gray-300">                                                                                                                           |
                |                                   |                         <thead id="reservationTableHead" class="bg-gray-200">                                                                                                                            |
                |                                   |                             <tr>                                                                                                                                                                         |
                |                                   |                                 <th class="py-2 px-4 border-b">Resource name</th>                                                                                                                        |
                |                                   |                                 <th class="py-2 px-4 border-b">Reservation start</th>                                                                                                                    |
                |                                   |                                 <th class="py-2 px-4 border-b">Reservation end</th>                                                                                                                      |
                |                                   |                                 <!--<th id="reserverHead" class="py-2 px-4 border-b">Reserver</th>-->                                                                                                    |
                |                                   |                             </tr>                                                                                                                                                                        |
                |                                   |                         </thead>                                                                                                                                                                         |
                |                                   |                         <tbody id="reservationTable">                                                                                                                                                    |
                |                                   |                             <!-- Dynamic table rows injected here -->                                                                                                                                    |
                |                                   |                         </tbody>                                                                                                                                                                         |
                |                                   |                     </table>                                                                                                                                                                             |
                |                                   |                 </div>                                                                                                                                                                                   |
                |                                   |             </div>                                                                                                                                                                                       |
                |                                   |         </div>                                                                                                                                                                                           |
                |                                   |         </main>                                                                                                                                                                                          |
                |                                   |         <!-- Footer -->                                                                                                                                                                                  |
                |                                   |         <div id="footer-placeholder"></div>                                                                                                                                                              |
                |                                   |         <script src="/static/footer.js"></script>                                                                                                                                                        |
                |                                   |         <script src="/static/index.js"></script>                                                                                                                                                         |
                |                                   |     </body>                                                                                                                                                                                              |
                |                                   |     </html>                                                                                                                                                                                              |
                +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
                | Parameter                         |     x-frame-options                                                                                                                                                                                      |
                +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
                | Solution                          | Modern Web browsers support the Content-Security-Policy and X-Frame-Options HTTP headers. Ensure one of them is set on all web pages returned by your site/app.                                          |
                |                                   |                                                                                                                                                                                                          |
                |                                   | If you expect the page to be framed only by pages on your server (e.g. it\'s part of a FRAMESET) then you\'ll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should    |
                |                                   | use DENY. Alternatively consider implementing Content Security Policy\'s \"frame-ancestors\" directive.                                                                                                  |
                +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
    :::
:::

:::: {#appendix .section .appendix}
## Appendix

::: {#alert-types .section .alert-types}
### Alert types

This section contains additional information on the types of alerts in
the report.

1.  ::: {#alert-type-0}
    #### Missing Anti-clickjacking Header

    +-----------------------------------+-------------------------------------------------------------------------------------------+
    | Source                            | raised by a passive scanner ([Anti-clickjacking                                           |
    |                                   | Header](https://www.zaproxy.org/docs/alerts/10020/))                                      |
    +-----------------------------------+-------------------------------------------------------------------------------------------+
    | CWE ID                            | [1021](https://cwe.mitre.org/data/definitions/1021.html)                                  |
    +-----------------------------------+-------------------------------------------------------------------------------------------+
    | WASC ID                           | 15                                                                                        |
    +-----------------------------------+-------------------------------------------------------------------------------------------+
    | Reference                         | 1.  <https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/X-Frame-Options> |
    +-----------------------------------+-------------------------------------------------------------------------------------------+
    :::
:::
::::
