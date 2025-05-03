---
layout: home
---

<!-- Wrapper for the portfolio section, displaying a list of projects -->
<!-- Wrapper for the portfolio section, displaying a list of projects -->
<div class="portfolio" style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: center;">
  {% if site.data.projects %}
    {% for project in site.data.projects %}
      <div class="project-card" style="border: 1px solid #ddd; border-radius: 8px; padding: 20px; width: 300px; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);">
        <h2 style="font-size: 1.5em; margin-bottom: 10px;">{{ project.title }}</h2>
        <p style="color: #555; margin-bottom: 15px;">{{ project.description }}</p>
        <!-- Centered View Project Link -->
        <div style="text-align: center; margin-top: 15px;">
          <a href="{{ project.link }}" style="text-decoration: none; color: #007acc; font-weight: bold;">View Project →</a>
        </div>
      </div>
    {% endfor %}
  {% else %}
    <p>No projects available at the moment.</p>
  {% endif %}
</div>
<div class="timeline" style="position: relative; margin: 50px auto; padding: 20px; max-width: 800px;">
  <!-- Vertical line -->
  <div style="position: absolute; left: 20px; top: 0; bottom: 0; width: 2px; background-color: #ddd;"></div>

  {% assign experiences = site.data.experiences %}
  {% if experiences %}
    {% for experience in experiences %}
      <div class="timeline-item" style="position: relative; margin-bottom: 50px;">
        <!-- Bubble -->
        <div class="timeline-bubble" style="position: absolute; left: -20px; top: 0; width: 40px; height: 40px; background-color: #007acc; border-radius: 50%; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);"></div>
        
        <!-- Content -->
        <div class="timeline-content" style="margin-left: 60px; padding: 20px; background: #f9f9f9; border-radius: 8px; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);">
          <h3 style="margin: 0 0 10px;">{{ experience.title }}</h3>
          <p style="margin: 0 0 5px; color: #555;"><strong>{{ experience.company }}</strong> - {{ experience.date }}</p>
          <p style="margin: 0; color: #777;">{{ experience.description }}</p>
          
          <!-- Show More Section -->
          <div class="more-details" style="display: none; margin-top: 10px; color: #555;">
            <p>{{ experience.details }}</p>
          </div>
          <button class="toggle-details" style="margin-top: 10px; padding: 5px 10px; background-color: #007acc; color: white; border: none; border-radius: 4px; cursor: pointer;">
            Show More
          </button>
        </div>
      </div>
    {% endfor %}
  {% else %}
    <p>No work experience available at the moment.</p>
  {% endif %}

  <!-- "... and more" Section -->
  <p style="text-align: center; margin-top: 30px; font-size: 0.9em; color: #555; font-style: italic;">
    ... and more
  </p>
</div>
<!-- Popup Warning -->
<div id="popup-warning" style="position: fixed; top: 0; left: 0; width: 100%; height: 100%; background-color: rgba(0, 0, 0, 0.8); display: flex; justify-content: center; align-items: center; z-index: 1000;">
  <div style="background: white; padding: 20px; border-radius: 8px; max-width: 400px; text-align: center; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);">
    <h2 style="margin-bottom: 15px;">Notice</h2>
    <p style="margin-bottom: 20px; color: #555;">
      This website is under construction. Information may be inaccurate or satirical. No liability is assumed for defects or bugs.
    </p>
    <button id="agree-button" style="padding: 10px 20px; background-color: #007acc; color: white; border: none; border-radius: 4px; cursor: pointer;">
      I Understand
    </button>
  </div>
</div>

<script>
  document.addEventListener("DOMContentLoaded", function () {
    const popup = document.getElementById("popup-warning");
    const agreeButton = document.getElementById("agree-button");

    agreeButton.addEventListener("click", function () {
      popup.style.display = "none";
    });
  });
</script>
<script>
  document.addEventListener("DOMContentLoaded", function () {
    const buttons = document.querySelectorAll(".toggle-details");
    buttons.forEach(button => {
      button.addEventListener("click", function () {
        const details = this.previousElementSibling;
        if (details.style.display === "none") {
          details.style.display = "block";
          this.textContent = "Show Less";
        } else {
          details.style.display = "none";
          this.textContent = "Show More";
        }
      });
    });
  });
</script>