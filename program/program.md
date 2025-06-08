---
 layout: "multilevel_navbar"
 background: '/img/bg-index.jpg'
---
<style>
    a.custom-link {
      color: #428bca !important;
    }
    @media (max-width: 767px) {
      .table-responsive table,
      .table-responsive thead,
      .table-responsive tbody,
      .table-responsive th,
      .table-responsive td,
      .table-responsive tr {
        display: block;
        width: 100%;
      }
      .table-responsive thead {
        display: none;
      }
      .table-responsive tr {
        margin-bottom: 1rem;
        border: 1px solid #dee2e6;
        border-radius: 0.5rem;
        box-shadow: 0 2px 4px rgba(0,0,0,0.03);
        background: #fff;
        padding: 0.5rem;
      }
      .table-responsive td {
        border: none;
        position: relative;
        padding-left: 0;
        min-height: 40px;
        box-sizing: border-box;
        padding-bottom: 0;
      }
      .accordion-tap {
        display: block;
        width: 100%;
        background: #f7f7f7;
        border-radius: 0.3rem;
        padding: 0.7rem 1rem;
        font-weight: bold;
        color: #333;
        cursor: pointer;
        border: 1px solid #e0e0e0;
        margin-bottom: 0.3rem;
      }
      .accordion-details {
        display: none;
        padding: 0.5rem 1rem 0.5rem 1rem;
        border-top: 1px solid #eee;
        background: #fff;
      }
      .accordion-tap.active + .accordion-details {
        display: block;
      }
    }
</style>
# Program

<!-- <div class="download-panel" style="background-color: #f8f9fa; border: 1px solid #dee2e6; border-radius: 8px; padding: 20px; margin: 20px 0; text-align: center;">
  <h4 style="margin-bottom: 15px; color: #333;">Download Conference Proceedings</h4>
  <a href="https://hpcrl.github.io/ICS2025-webpage/program/Proceedings_ICS25" class="btn btn-primary" style="background-color: #428bca; color: white; padding: 10px 20px; text-decoration: none; border-radius: 5px; display: inline-block;">
    <i class="fas fa-download" style="margin-right: 8px;"></i>Download Papers
  </a>
</div> -->

## 06/09/2025 Monday
<div class="table-responsive">
     <table class="table table-bordered align-middle" style="table-layout: fixed; width: 100%;">
      <thead class="table-dark">
        <tr>
          <th style="width: 150px; background-color: #000;">Time</th>
          <th style="background-color: #000;">Track A (Ballroom AB)</th>
          <th style="background-color: #000;">Track B (Ballroom C)</th>
        </tr>
      </thead>
      <tbody>
        {% for row in site.data.day1 %}
          {% assign session1 = row.Session1 %}
          {% assign session2 = row.Session2 %}

        {% if row.Session1.Session == "Keynote"%}
            <tr>
              <td data-label="Time">{{ row.Time }}</td>
              <td colspan="2">
                <span class="accordion-tap"> <strong>{{ "Keynote Talk (Ballroom AB)" }}</strong></span>
                <div class="accordion-details">
                  <a href="https://hpcrl.github.io/ICS2025-webpage/keynote/keynote.html" class="custom-link"> <strong>{{ session1.Title }}</strong></a><br>
                  {{ session1.Author }}<br>
                </div>
              </td>
            </tr>
         {% elsif row.Session1.Session == "Opening"%}
            <tr>
              <td data-label="Time">{{ row.Time }}</td>
              <td colspan="2">
                <span class="accordion-tap"> {{ session1.Session }}</span>
              </td>
            </tr>
          {% elsif row.Session1.Session == "Coffee Break"%}
            <tr>
              <td data-label="Time">{{ row.Time }}</td>
              <td colspan="2">
                <span class="accordion-tap"> {{ session1.Session }}</span>
              </td>
            </tr>
          {% elsif row.Session1.Session == "Lunch (provided)"%}
            <tr>
              <td data-label="Time">{{ row.Time }}</td>
              <td colspan="2">
                <span class="accordion-tap"> {{ session1.Session }}</span>
              </td>
            </tr>
          {% elsif row.Session1.Session == "Breakfast"%}
            <tr>
              <td data-label="Time">{{ row.Time }}</td>
              <td colspan="2">
                <span class="accordion-tap"> {{ session1.Session }}</span>
              </td>
            </tr>
          {% else %}
            <tr>
              <td data-label="Time">{{ row.Time }}</td>
  
              <!-- Session 1 -->
              <td data-label="Session 1">
                <span class="accordion-tap"> Session: {{ session1.Session }}</span>
                <div class="accordion-details">

                  Chair: {{ session1.Chair }}<br>
                  {% if session1.Papers and session1.Papers != empty %}
                    <ul class="mb-0">
                      {% for paper in session1.Papers %}
                        <li>
                          {% if paper.URL %}
                            <a href="{{ paper.URL }}" target="_blank" class="custom-link">{{ paper.Title }}</a>
                            {% if paper.Comment %}
                            <div class="text-muted small">{{ paper.Comment }}</div>
                            {% endif %}
                          {% else %}
                            {{ paper.Title }}
                          {% endif %}
                           <div class="text-muted small">{{ paper.Author }}</div>
              
                        </li>
                      {% endfor %}
                    </ul>
                  {% else %}
                    <em>No papers for this session</em>
                  {% endif %}
                </div>
              </td>
  
              <!-- Session 2 -->
              <td data-label="Session 2">
                <span class="accordion-tap"> Session: {{ session2.Session }}</span>
                <div class="accordion-details">
 
                  Chair: {{ session2.Chair }}<br>
                  {% if session2.Papers and session2.Papers != empty %}
                    <ul class="mb-0">
                      {% for paper in session2.Papers %}
                        <li>
                          {% if paper.URL %}
                            <a href="{{ paper.URL }}" target="_blank" class="custom-link">{{ paper.Title }}</a>
                             {% if paper.Comment %}
                              <div class="text-muted small">{{ paper.Comment }}</div>
                            {% endif %}
                          {% else %}
                            {{ paper.Title }}
                          {% endif %}
                           <div class="text-muted small">{{ paper.Author }}</div>
                          
                        </li>
                      {% endfor %}
                    </ul>
                  {% else %}
                    <em>No papers for this session</em>
                  {% endif %}
                </div>
              </td>
            </tr>
          {% endif %}
        {% endfor %}
      </tbody>
    </table>
  </div>




## 06/10/2025 Tuesday
<div class="table-responsive">
    <table class="table table-bordered align-middle" style="table-layout: fixed; width: 100%;">
      <thead class="table-dark">
        <tr>
          <th style="width: 150px; background-color: #000;">Time</th>
          <th style="background-color: #000;">Track A (Ballroom AB)</th>
          <th style="background-color: #000;">Track B (Ballroom C)</th>
        </tr>
      </thead>
      <tbody>
        {% for row in site.data.day2 %}
          {% assign session1 = row.Session1 %}
          {% assign session2 = row.Session2 %}

          {% if row.Session1.Session == "Coffee Break"%}
          <tr>
            <td data-label="Time">{{ row.Time }}</td>
            <td colspan="2">
              <span class="accordion-tap"> {{ session1.Session }}</span>
            </td>
          </tr>
        {% elsif row.Session1.Session == "Lunch (provided)"%}
          <tr>
            <td data-label="Time">{{ row.Time }}</td>
            <td colspan="2">
              <span class="accordion-tap"> {{ session1.Session }}</span>
            </td>
          </tr>
          {% elsif row.Session1.Session == "Excursion"%}
          <tr>
            <td data-label="Time">{{ row.Time }}</td>
            <td colspan="2">
              <span class="accordion-tap"> {{ session1.Info }}</span>
            </td>
          </tr>
           {% elsif row.Session1.Session == "Breakfast"%}
            <tr>
              <td data-label="Time">{{ row.Time }}</td>
              <td colspan="2">
                <span class="accordion-tap"> {{ session1.Session }}</span>
              </td>
            </tr>
        {% elsif row.Session1.Session == "Excursion"%}
          <tr>
            <td data-label="Time">{{ row.Time }}</td>
            <td colspan="2">
              <span class="accordion-tap"> {{ session1.Session }}</span>
            </td>
          </tr>
        {% elsif row.Session1.Session == "Best Papers"%}
            <tr>
              <td data-label="Time">{{ row.Time }}</td>
              <td colspan="2">
                <span class="accordion-tap"> <strong> Session: {{ session1.Session }} (Ballroom AB)</strong> </span>
                <div class="accordion-details">

                  Chair: {{ session1.Chair }}<br>
                  {% if session1.Papers and session1.Papers != empty %}
                    <ul class="mb-0">
                      {% for paper in session1.Papers %}
                        <li>
                          {% if paper.URL %}
                            <a href="{{ paper.URL }}" target="_blank" class="custom-link">{{ paper.Title }}</a>
                             {% if paper.Comment %}
                            <div class="text-muted small">{{ paper.Comment }}</div>
                            {% endif %}
                          {% else %}
                            {{ paper.Title }}
                          {% endif %}
                           <div class="text-muted small">{{ paper.Author }}</div>
                         
                        </li>
                      {% endfor %}
                    </ul>
                  {% else %}
                    <em>No papers for this session</em>
                  {% endif %}
                </div>
              </td>
            </tr>
          {% else %}
            <tr>
              <td data-label="Time">{{ row.Time }}</td>
  
              <!-- Session 1 -->
              <td data-label="Session 1">
                <span class="accordion-tap"> Session: {{ session1.Session }}</span>
                <div class="accordion-details">

                  Chair: {{ session1.Chair }}<br>
                  {% if session1.Papers and session1.Papers != empty %}
                    <ul class="mb-0">
                      {% for paper in session1.Papers %}
                        <li>
                          {% if paper.URL %}
                            <a href="{{ paper.URL }}" target="_blank" class="custom-link">{{ paper.Title }}</a>
                             {% if paper.Comment %}
                            <div class="text-muted small">{{ paper.Comment }}</div>
                            {% endif %}
                          {% else %}
                            {{ paper.Title }}
                          {% endif %}
                           <div class="text-muted small">{{ paper.Author }}</div>
                        
                        </li>
                      {% endfor %}
                    </ul>
                  {% else %}
                    <em>No papers for this session</em>
                  {% endif %}
                </div>
              </td>
  
              <!-- Session 2 -->
              <td data-label="Session 2">
                <span class="accordion-tap"> Session: {{ session2.Session }}</span>
                <div class="accordion-details">
 
                  Chair: {{ session2.Chair }}<br>
                  {% if session2.Papers and session2.Papers != empty %}
                    <ul class="mb-0">
                      {% for paper in session2.Papers %}
                        <li>
                          {% if paper.URL %}
                            <a href="{{ paper.URL }}" target="_blank" class="custom-link">{{ paper.Title }}</a>
                             {% if paper.Comment %}
                            <div class="text-muted small">{{ paper.Comment }}</div>
                            {% endif %}
                          {% else %}
                            {{ paper.Title }}
                          {% endif %}
                           <div class="text-muted small">{{ paper.Author }}</div>
                       
                        </li>
                      {% endfor %}
                    </ul>
                  {% else %}
                    <em>No papers for this session</em>
                  {% endif %}
                </div>
              </td>
            </tr>
          {% endif %}
        {% endfor %}
      </tbody>
    </table>
  </div>

## 06/11/2025 Wednesday
<div class="table-responsive">
     <table class="table table-bordered align-middle" style="table-layout: fixed; width: 100%;">
      <thead class="table-dark">
        <tr>
          <th style="width: 150px; background-color: #000;">Time</th>
          <th style="background-color: #000;">Track A (Ballroom AB)</th>
          <th style="background-color: #000;">Track B (Ballroom C)</th>
        </tr>
      </thead>
      <tbody>
        {% for row in site.data.day3 %}
          {% assign session1 = row.Session1 %}
          {% assign session2 = row.Session2 %}

          {% if row.Session1.Session == "Coffee Break"%}
          <tr>
            <td data-label="Time">{{ row.Time }}</td>
            <td colspan="2">
              <span class="accordion-tap">  {{ session1.Session }}</span>
            </td>
          </tr>
        {% elsif row.Session1.Session == "Lunch (provided)"%}
          <tr>
            <td data-label="Time">{{ row.Time }}</td>
            <td colspan="2">
              <span class="accordion-tap"> {{ session1.Session }}</span>
            </td>
          </tr>
           {% elsif row.Session1.Session == "Breakfast"%}
            <tr>
              <td data-label="Time">{{ row.Time }}</td>
              <td colspan="2">
                <span class="accordion-tap"> {{ session1.Session }}</span>
              </td>
            </tr>
          {% else %}
            <tr>
              <td data-label="Time">{{ row.Time }}</td>
  
              <!-- Session 1 -->
              <td data-label="Session 1">
                <span class="accordion-tap"> Session: {{ session1.Session }}</span>
                <div class="accordion-details">

                  Chair: {{ session1.Chair }}<br>
                  {% if session1.Papers and session1.Papers != empty %}
                    <ul class="mb-0">
                      {% for paper in session1.Papers %}
                        <li>
                          {% if paper.URL %}
                            <a href="{{ paper.URL }}" target="_blank" class="custom-link">{{ paper.Title }}</a>
                             {% if paper.Comment %}
                            <div class="text-muted small">{{ paper.Comment }}</div>
                            {% endif %}
                          {% else %}
                            {{ paper.Title }}
                          {% endif %}
                           <div class="text-muted small">{{ paper.Author }}</div>
                         
                        </li>
                      {% endfor %}
                    </ul>
                  {% else %}
                    <em>No papers for this session</em>
                  {% endif %}
                </div>
              </td>
  
              <!-- Session 2 -->
              <td data-label="Session 2">
                <span class="accordion-tap"> Session: {{ session2.Session }}</span>
                <div class="accordion-details">
 
                  Chair: {{ session2.Chair }}<br>
                  {% if session2.Papers and session2.Papers != empty %}
                    <ul class="mb-0">
                      {% for paper in session2.Papers %}
                        <li>
                          {% if paper.URL %}
                            <a href="{{ paper.URL }}" target="_blank" class="custom-link">{{ paper.Title }}</a>
                             {% if paper.Comment %}
                            <div class="text-muted small">{{ paper.Comment }}</div>
                            {% endif %}
                          {% else %}
                            {{ paper.Title }}
                          {% endif %}
                           <div class="text-muted small">{{ paper.Author }}</div>
                          
                        </li>
                      {% endfor %}
                    </ul>
                  {% else %}
                    <em>No papers for this session</em>
                  {% endif %}
                </div>
              </td>
            </tr>
          {% endif %}
        {% endfor %}
      </tbody>
    </table>
  </div> 


<script>
document.addEventListener('DOMContentLoaded', function() {
  if (window.innerWidth <= 767) {
    document.querySelectorAll('.accordion-tap').forEach(function(tap) {
      tap.addEventListener('click', function(e) {
        e.stopPropagation();
        this.classList.toggle('active');
        var details = this.nextElementSibling;
        if (details.style.display === 'block') {
          details.style.display = 'none';
        } else {
          details.style.display = 'block';
        }
      });
    });
  }
});
</script>
