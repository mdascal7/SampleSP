## **Introduction** ##
### **Summary** ###
HYPER is a homegrown Performance Testing Tool, build entirely from open source components, that enables engineers to execute performance tests on their own, without any dependencies. The user is able to monitor the test in Real Time, while the test is running, and at the end of the test get the Test Report over Email; and it can also be integrated with Slack, to receive the Test Report on the dedicated Slack Channel. It allows Engineers to build and modify tests quickly and easily, offering considerable time savings with minimal-to-none outside help.
### **Key Features** ###

 - Ability to run performance tests without performance engineering team involvement
 - No licensing or other third party costs involved, as the tool is build in-house from open source components
 - Estimated time-savings of 7 hours minimum of combined Performance+DevEngineer time for basic API tests
 - For existing tests, you can modify the API's Endpoint URL, Data Files, Workload Model etc. quickly and, easily
 - Readily observe and identify your project's performance trends and plan accordingly
 - The Slack integration allows you to post the test reports on the dedicated channel
 - All Stats are in one place; easy to understand your app/api performance at a glance
 - Ability to monitor your test in Real Time, while the test is executing
 - All Infrastructure in on *OneOps* and it is easily scalable
### **Use Cases** ###
**CI/CD/CP**
 
 - New Service
 - Existing Service - New API
 - Existing Service - Existing API
 - Orchestration Layer
 - Orchestration Layer with New Services
 - Page Level
 - Page Groups
 - Data Variation for all the above Use cases
 - Services with Dependency among multiple APIs

**Scheduled and On Demand - (Includes CI/CD/CP use cases)**

 - E2E Testing (lower environments)
 - Scalability Testing
 - Throughput Testing
 - Benchmarking Testing
	 - Hardware
	 - Software
 - Spike Testing

**Reports**

 - Test summary report
 - Live Performance Test Monitoring using Medusa
 - Continuous Performance (Pipeline)
### **Architecture** ###
![HyperCurrentArchitecturePage1JPEG](https://confluence.walmart.com/download/attachments/209950455/Hyper_Current_Architecture%20-%20Page%201.jpeg?api=v2)
### **Feature List** ###
<strong>Production Performance test</strong>
<ul>
  <li>MVP: Able to run from public cloud - No AWS agents   </li>
  <li>MVP: Locations for Public cloud agents (US)</li>
  <li>Locations for Public cloud agents (UK, Canada)</li>
  <li>MVP: Able to handle - 60M PageViews/Hr and 10K OPM at minimum</li>
  <li>MVP: Able to control individual scripts' VUs while test execution</li>
  <li>Enable certain percentage to log request and response data in the test tool<br/>
  </li>
</ul>
<p>
  <strong>Internal Performance Test</strong>
</p>
<ul>
  <li>MVP: Able to reach ~60K TPS<br/>
  </li>
</ul>
<p>
  <strong>Test Manager </strong>
</p>
<ul>
  <li>MVP: Should spin up test controllers</li>
  <li>Control load based on feedback data (ramp up, down or stop) for complex load tests (multiple components, end-to-end)<ul>
      <li>Need to define feedback data for ramping</li>
    </ul>
  </li>
  <li>MVP: Start, stop, abort tests</li>
  <li>MVP: Kill switch for individual sub-test or overall tests</li>
  <li>Schedule tests</li>
  <li>MVP: Gating: detect overlap and limit </li>
  <li>Service discovery</li>
  <li>MVP: Queueing of tests</li>
  <li>MVP: Ability to spin up test infrastructure by OneOps Org</li>
</ul>
<p>
  <strong>
    <strong>Test Project and User Portal</strong>
  </strong>
</p>
<ul>
  <li>MVP: Roles Management (Assign 5 Roles: Super Admin, Admin, Performance Engineer, Read Only, Anonymous)</li>
  <li>MVP: Ability to login using HO userid</li>
  <li>MVP: View and compare historic results</li>
  <li>MVP: Ability to upload test projects (.jmx and .yaml)</li>
  <li>MVP: Maintain uploaded tests plans for future reference</li>
  <li>MVP: Ability to kickoff tests from GIT repo</li>
</ul>
<p>
  <strong>
  </strong>
</p>
<p>
  <strong>Test Controllers</strong>
</p>
<ul>
  <li>MVP: Spin up and control the executors dynamically based on defined load and state of the executers (auto-scale)</li>
  <li>MVP: Monitor executors, OS level, error counts, etc.</li>
  <li>MVP: Controller needs to aggregate test results.</li>
  <li>MVP: Kill runaway executors</li>
</ul>
<p>
  <strong>

  </strong>
</p>
<p>
  <strong>Scripting</strong>
</p>
<ul>
  <li>Recording the flow</li>
  <li>MVP: Adding validation on response (HTTP response codes are not sufficient, need to check for internal error codes ann response data)  </li>
  <li>MVP: Correlate response and parse (complex flows, using response data for subsequent requests, need to be available for body, header and URL)</li>
  <li>MVP: Support create random input data for requests for strings and other data type, should be able to utilize external code.</li>
  <li>MVP: Multi column CSV file (seed data where one column in row depends on a value from another column)</li>
  <li>Script validation</li>
  <li>MVP: Ability to suppress images and 3rd party requests (example: no calls to Visa for checkout flows, suppress ads, etc. )</li>
  <li>Ability to suppress specific errors or warnings</li>
  <li>Multiple ways of error handling<ul>
      <li>MVP: Stop on error</li>
      <li>Continue on error</li>
      <li>Retry on error (specify max number of retries, retry from step one of flow)</li>
    </ul>
  </li>
  <li>MVP: Headers (add customer header to request, manipulate header, add, modify or remove stuff from headers)</li>
  <li>MVP: Cookies management (e.g. add, remove, change value, delete all or subset of cookies for domain in test browser) </li>
  <li>Enable or disable caching option - All request will be like first time visitor</li>
  <li>MVP: Disable caching option - All request will be like first time visitor</li>
  <li>MVP: Ability to hit specific ports for IPs, host names or VIPs </li>
  <li>Profile types and user types (e.g. debug users, enable debug information for subset of test users, flows can also differ between user types. leave out steps, use different path)  </li>
  <li>MVP: Different type of workload modeling (e.g. dynamic ramp-up and down based on feedback, ability to script not dynamic ramp up and down) </li>
  <li>Import and export projects (build new test scripts based on existing scripts)</li>
  <li>Debug statements on log files (include additional information to log files for script debugging purposes)</li>
  <li>MVP: Session management (test user)</li>
  <li>Cross browser and device support (specify browser/ device mix in script, also ability to simulate network speed by device)</li>
  <li>MVP: Think and pacing for user actions</li>
  <li>Synchronization functions (control how many users execute a particular step at the same time)</li>
  <li>Define granularity of real-time result reporting, also applies to reporting in general </li>
  <li>MVP: Ability to define custom timers (e.g. single time for multiple steps)</li>
  <li>MVP: Auto Test plan generation for single API/service test</li>
  <li>Custom functions, i.e. reusable, extensible library of common somewhat high-level functionality  </li>
</ul>
<p>
  <strong>Real Time Monitoring</strong>
</p>
<ul>
  <li>MVP: For each Request Response Time count, min, max and Avg per sec</li>
  <li>MVP: Hits/sec</li>
  <li>MVP: Errors/sec</li>
  <li>MVP: HTTP Pages/sec</li>
</ul>
<p>
  <strong>
  </strong>
</p>
<p>
  <strong>Reporting</strong>
</p>
<ul>
  <li>MVP: Summary Report</li>
  <li>MVP: Real-time Time series data</li>
  <li>MVP: Page level stats</li>
  <li>Graph for all the data related to test</li>
  <li>MVP: Error Info (Breakdown by response/code or error code)</li>
  <li>Network stats</li>
  <li>Integrate with APP and OS metrics</li>
  <li>CDN/Torbit data</li>
  <li>DB data</li>
  <li>MVP: Test infrastructure utilization (scheduled tests, test run status, #tests running, #tests scheduled, #tests finished) </li>
  <li>MVP: Test Data persistence</li>
  <li>MVP: Ability to compare results between different runs</li>
  <li>MVP: Email results</li>
  <li>MVP: Integration with Slack</li>
</ul>
<p>
  <strong>     </strong>
</p>
<p>
  <strong>CI CD/Self-Service/On-Demand</strong>
</p>
<ul>
  <li>MVP: Gating - Service Dependency</li>
  <li>MVP: Throttling -- Duration, No of threads, environment</li>
  <li>MVP: Mocking for CI/CD and Component Tests</li>
  <li>Restrictions -- (only non-prod)</li>
  <li>Quota and priority (e.g. locks)</li>
  <li>DC Level or cloud level selection with localized test executors</li>
  <li>MVP: Single-Sign on for On-Demand/Self Service</li>
  <li>MVP: Audit Trail<br/>
  </li>
</ul>

### **Customers**###

 - CAGM
 - GOP
 - Promotions
 - Sam's Club
 - USGM
 - Walmart Core

	**(Over 150 Projects Ported!)**
