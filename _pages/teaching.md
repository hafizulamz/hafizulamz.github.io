---
layout: page
permalink: /teaching/
title: teaching
description: classes, workshops, and teaching materials.
nav: true
nav_order: 3
display_categories: [Universiti Teknologi PETRONAS, Universiti Tun Hussein Onn Malaysia]
horizontal: false
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/teaching.jpg" title="teaching experiences" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<b>My teaching philosophy</b>: I'm a passionate educator dedicated to engaging students in `Active Learning` and `Outcome Based Education`. Experienced in teaching small and large groups while fostering `positive relationships` with students.

<div class="projects">
  <h2 class="category">metrics</h2>
</div>
<div class="row mt-3">
  <div class="col-sm mt-3 mt-md-0">
    <a hrefxx="" style="text-decoration:none">
      <div class="card hoverable"><div class="card-body">
        <p class="card-text">Teaching Performance Rating</p>
	<h2 class="card-title text-lowercase">4.91 / 5.0</h2>
        <p class="card-text">based on 66 responses</p>
      </div></div>
    </a>
  </div>
  <div class="col-sm mt-3 mt-md-0">
    <a hrefxx="" style="text-decoration:none">
      <div class="card hoverable"><div class="card-body">
        <p class="card-text">Student Support Rating</p>
	<h2 class="card-title text-lowercase">4.94 / 5.0</h2>
        <p class="card-text">based on 66 responses</p>
      </div></div>
    </a>
  </div>
</div>


<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}
{% endif %}
</div>







<h3 class="mt-4">Universiti Teknologi PETRONAS</h3>

<div class="card mt-3">
  <div class="p-3">
    <div class="row">
      <div class="col-sm-10">
        <h5 class="font-weight-bold">Enterprise Resource Planning</h5>
      </div>
      <div class="col-sm-2 text-left text-sm-right">
        <span class="badge font-weight-bold warning-color-dark text-uppercase align-middle">Tutorial</span>
      </div>
    </div>
    <h6 class="font-italic mt-2 mt-sm-0">GA Tutor: May 23</h6>
    <ul>
      <li>Business process and business functions</li>
	    <li>ERP system development</li>
	    <li>Sales order process</li>
      <li>Customer Relationship Management (CRM)</li>
      <li>Production planning</li>
      <li>Sales forecast and sales operations planning</li>
      <li>Supply Chain Management (SCM)</li>
      <li>Human Resource (HR) and Process Modeling </li>
	</ul>
  </div>
</div>

<div class="card mt-3">
  <div class="p-3">
    <div class="row">
      <div class="col-sm-10">
        <h5 class="font-weight-bold">Business Intelligence</h5>
      </div>
      <div class="col-sm-2 text-left text-sm-right">
        <span class="badge font-weight-bold warning-color-dark text-uppercase align-middle">Hands-On Lab</span>
      </div>
    </div>
    <h6 class="font-italic mt-2 mt-sm-0">GA Tutor: Jan 21, Sep 21, Jan 22, Sep 22</h6>
    <ul>
      <li>Data analysis, cleansing, and preparation</li>
      <li>Data visualization, Pivot tables and charts</li>
      <li>Preparation of an Excel dashboard</li>
      <li>Install, design, and deploy Power BI dashboard: <a href="https://youtu.be/3BOummMBNJU">video</a></li>
      <li>DAX query, forecasting, and Python on Power BI: <a href="https://youtu.be/KeLI6O5ATaE">video</a></li>
      <li>Datasets: <a href="https://2a10589f-c553-479d-8abf-7980cc48fb12.filesusr.com/ugd/e8f2f2_8bf7af4f1f784dc586b7fbeebfd30012.xlsx?dn=2015%20Sales.xlsx">Sales</a>, <a href="https://2a10589f-c553-479d-8abf-7980cc48fb12.filesusr.com/ugd/e8f2f2_287d6522d075446e8f75b9513da30440.xlsx?dn=HR%20Data-26112019-Cleansed.xlsx">HR Data</a>, <a href="https://2a10589f-c553-479d-8abf-7980cc48fb12.filesusr.com/ugd/e8f2f2_399460a4bb4d4faa840ab8ae7ab1e175.xlsx?dn=Superstore%20(Raw%20data).xlsx">Superstore</a>, <a href="https://2a10589f-c553-479d-8abf-7980cc48fb12.filesusr.com/ugd/e8f2f2_3d66dba3f35f445887873d3e4ac9c169.xlsx?dn=Voting%20figures.xlsx">Votes</a></li>
    </ul>
  </div>
</div>

<div class="card mt-3">
  <div class="p-3">
    <div class="row">
      <div class="col-sm-10">
        <h5 class="font-weight-bold">Big Data Analytics</h5>
      </div>
      <div class="col-sm-2 text-left text-sm-right">
        <span class="badge font-weight-bold warning-color-dark text-uppercase align-middle">Hands-On Lab</span>
      </div>
    </div>
    <h6 class="font-italic mt-2 mt-sm-0">GA Tutor: Jan 21, Sep 21, Sep 22, Jan 23</h6>
  	<ul>
      <li>Software and environment setup</li>
      <li>Big data systems: HDFS, Mapreduce, Hive, Spark</li>
      <li>Unstructured database: Hbase and NoSql</li>
      <li>Setting up Python environment and IDE</li>
      <li>Data cleansing and preparation</li>
      <li>Data visualization</li>
      <li>Fundamental of machine learning using Python</li>
      <li>Run machine learning models</li>
      <li>Generate reports</li>
    </ul>
  </div>
</div>

<div class="card mt-3">
  <div class="p-3">
    <div class="row">
      <div class="col-sm-10">
        <h5 class="font-weight-bold">IT/IS Project Management</h5>
      </div>
      <div class="col-sm-2 text-left text-sm-right">
        <span class="badge font-weight-bold warning-color-dark text-uppercase align-middle">Hands-On Lab</span>
      </div>
    </div>
    <h6 class="font-italic mt-2 mt-sm-0">GA Tutor: May 22, Jan 23, May 23</h6>
    <ul>
      <li>Create Work Breakdown Structure (WBS) and Gantt chart using ProjectLibre: <a href="https://youtu.be/9xwR4JCBaIU">video</a></li>
      <li>Managing resources: Setup and assign resources to tasks using ProjectLibre</li>
      <li>Create a project network diagram using ADM and Critical Path Analysis (CPA/CPM)</li>
      <li>CPA using Precedence Diagramming Method (PDM)</li>
      <li>Project management tool: SWOT analysis</li>
    </ul>
  </div>
</div>

<div class="card mt-3">
  <div class="p-3">
    <div class="row">
      <div class="col-sm-10">
        <h5 class="font-weight-bold">IT Infrastructure</h5>
      </div>
      <div class="col-sm-2 text-left text-sm-right">
        <span class="badge font-weight-bold warning-color-dark text-uppercase align-middle">Lab & Tutorial</span>
      </div>
    </div>
    <h6 class="font-italic mt-2 mt-sm-0">GA Tutor: May 22</h6>
	  <ul>
      <li>Fundamental: Datacenter trends, components, and security</li>
      <li>IT infrastructure for an enterprise: Platform as a Service (PaaS)</li>
      <li>Microsoft Azure and microservices</li>
      <li>Database: Relational database, NoSQL database, and current trends</li>
      <li>Data and computer networks</li>
      <li>IP classes, network address, and host address</li>
      <li>Security aspect of IT infrastructure</li>
    </ul>
  </div>
</div>

<div class="card mt-3">
  <div class="p-3">
    <div class="row">
      <div class="col-sm-10">
        <h5 class="font-weight-bold">Information Security Management</h5>
      </div>
      <div class="col-sm-2 text-left text-sm-right">
        <span class="badge font-weight-bold warning-color-dark text-uppercase align-middle">Tutorial</span>
      </div>
    </div>
    <h6 class="font-italic mt-2 mt-sm-0">GA Tutor: May 21</h6>
  </div>
</div>

<h3 class="mt-4">Universiti Tun Hussein Onn Malaysia</h3>

<div class="card mt-3">
  <div class="p-3">
    <div class="row">
      <div class="col-sm-10">
        <h5 class="font-weight-bold">Undergraduate Final Year Project I & II</h5>
      </div>
      <div class="col-sm-2 text-left text-sm-right">
        <span class="badge font-weight-bold warning-color-dark text-uppercase align-middle">Supervision</span>
      </div>
    </div>
    <h6 class="font-italic mt-2 mt-sm-0">2017, 2018, 2019</h6>
	<ul>
      <li>Supervise undergraduate students for FYP I and FYP II courses</li>
    </ul>
  </div>
</div>

<h3 class="mt-4">workshops and trainings</h3>
<div class="col">
    <ul>
      <li>Assistant trainer for the "Digital Transformation for the Future of Works: Big Data, AI and Machine Learning" course by CeRDaS-UTP.</li>
      <li>Trainer for the 3 days course of "Business Analytics using Power BI for M&amp;H Department", UTP.</li>
	  <li><a href="https://www.pythoncheatsheet.org/">Some notes</a> on writing Python libraries.</li>
    </ul>
</div>
