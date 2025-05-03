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
        </div>
      </div>
    {% endfor %}
  {% else %}
    <p>No work experience available at the moment.</p>
  {% endif %}
</div>