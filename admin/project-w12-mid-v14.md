{% macro show_main_text() %}
<div id="main">

<tip-box>

Overview: <include src="project-timeline.md#mid-v14-overview" inline />
</tip-box>

**<big>Project Management:</big>**

* **Freeze features** around this time. Ensure the current product have all the features you intend to release at v1.4. Adding major changes after this point is risky. The remaining time is better spent fixing problems discovered late or on fine-tuning the product.  

**<big>Product:</big>**

* Consider increasing code coverage by adding more tests if it is lower than the level you would like it to be. Take note of <trigger trigger="click" for="modal:mid-v14-testingExpectations">our expectation on test code</trigger>. 
* After you have sufficient code coverage, fix remaining code quality problems and bring up the quality to your target level.

<modal title="Admin {{ icon_embedding }} Project Asessement → Expectation on testing" id="modal:mid-v14-testingExpectations">
  <include src="project-testing.fr#expectations"/>
</modal>

<div class="indented-level2">
<panel src="project-assessment.md#code-quality-tips" header="Admin {{ icon_embedding }} Project Asessement → Code Quality Tips" class="embedding" minimized />
</div>

**<big>Documentation:</big>**

* Update documentation to match the product.

* Create the first version of your _Project Portfolio Page (PPP)_. Reason: **Each member needs to create a PPP** to describe your contribution to the project. Creating a PPP takes a significant effort; it is ==too risky to leave it to the last week of the project==. 


<div class="indented-level2">
<panel src="project-deliverables.md#project-deliverables-ppp" header="Admin {{ icon_embedding }} Project → Deliverables → Project Portfolio Page" class="embedding" minimized />
</div>


**<big>Demo:</big>**

* Do a product demo to serve as a rehearsal for the final project demo at v1.4
  * ==Follow <trigger trigger="click" for="modal:mid-v14-demo-instructions">final demo instructions</trigger>== as much as possible.
  * **Cover all features**, not just the ones added in the recent iteration.
  * Try to make it **a 'well prepared' demo** i.e., know in advance exactly what you'll do in the demo.

<modal large title="Admin {{ icon_embedding }} Project → v1.4 Demo (extract)" id="modal:mid-v14-demo-instructions">
  <include src="project-deliverables.md#project-deliverables-demo"/>
</modal> 

</div>
{% endmacro %}

{% from "common/admin.njk" import show_admin_page with context %}
{{ show_admin_page("project-w12-mid-v14", show_main_text) }}