
<div class="timeline" style="position: relative; margin: 50px auto; padding: 20px; max-width: 800px;">
  <!-- Vertical line -->
  <div style="position: absolute; left: 20px; top: 0; bottom: 0; width: 2px; background-color: #ddd;"></div>

  {% assign projects = site.data.projects %}
  {% if projects %}
    {% for project in projects %}
      <div class="timeline-item" style="position: relative; margin-bottom: 50px;">
        <!-- Bubble -->
        <div class="timeline-bubble" style="position: absolute; left: -20px; top: 0; width: 40px; height: 40px; background-color: #007acc; border-radius: 50%; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);"></div>
        
        <!-- Content -->
        <div class="timeline-content" style="margin-left: 60px; padding: 20px; background: #f9f9f9; border-radius: 8px; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);">
          <h3 style="margin: 0 0 10px;">{{ project.title }}</h3>
          <p style="margin: 0 0 5px; color: #555;"><strong>{{ project.date }}</strong></p>
          <p style="margin: 0; color: #777;">{{ project.description }}</p>
          
          <!-- Show More Section -->
          <div class="more-details" style="display: none; margin-top: 10px; color: #555;">
            <p>{{ project.details }}</p>
          </div>
          <button class="toggle-details" style="margin-top: 10px; padding: 5px 10px; background-color: #007acc; color: white; border: none; border-radius: 4px; cursor: pointer;">
            Show More
          </button>
        </div>
      </div>
    {% endfor %}
  {% else %}
    <p>No projects available at the moment.</p>
  {% endif %}
</div>

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