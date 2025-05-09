---
 layout: "multilevel_navbar"
 background: '/img/bg-index.jpg'
---
<style>
    a.custom-link {
      color: #428bca !important;
    }
</style>
# Preliminary Schedule of Papers

## 06/09/2025 Monday
<div class="table-responsive">
     <table class="table table-bordered align-middle" style="table-layout: fixed; width: 100%;">
      <thead class="table-dark">
        <tr>
          <th style="width: 150px; background-color: #000;">Time</th>
          <th style="background-color: #000;">Session 1</th>
          <th style="background-color: #000;">Session 2</th>
        </tr>
      </thead>
      <tbody>
        {% for row in site.data.day1 %}
          {% assign session1 = row.Session1 %}
          {% assign session2 = row.Session2 %}

        {% if row.Keynote %}
        <tr>
            <td>{{ row.Time }}</td>
            <td colspan="2">
            <strong>Keynote:</strong>
            {% if row.Keynote.URL %}
                <a href="{{ row.Keynote.URL }}" target="_blank">{{ row.Keynote.Title }}</a>
            {% else %}
                {{ row.Keynote.Title }}
            {% endif %}
            <br><em>{{ row.Keynote.Author }}</em>
            </td>
        </tr>
        {% elsif row.Lunch %}
            <tr>
              <td>{{ row.Time }}</td>
              <td colspan="2" class="text-center"><strong>{{ row.Lunch.Comment }}</strong></td>
            </tr>
          {% else %}
            <tr>
              <td>{{ row.Time }}</td>
  
              <!-- Session 1 -->
              <td>
                <strong>Session: {{ session1.Session }}</strong><br>
                Chair: {{ session1.Chair }}<br>
                {% if session1.Papers and session1.Papers != empty %}
                  <ul class="mb-0">
                    {% for paper in session1.Papers %}
                      <li>
                        {% if paper.URL %}
                          <a href="{{ paper.URL }}" target="_blank" class="custom-link">{{ paper.Title }}</a>
                        {% else %}
                          {{ paper.Title }}
                        {% endif %}
                         <div class="text-muted small">{{ paper.Author }}</div>
                        {% if paper.Comment %}
                          <div class="text-muted small">{{ paper.Comment }}</div>
                        {% endif %}
                      </li>
                    {% endfor %}
                  </ul>
                {% else %}
                  <em>No papers for this session</em>
                {% endif %}
              </td>
  
              <!-- Session 2 -->
              <td>
                <strong>Session: {{ session2.Session }}</strong><br>
                Chair: {{ session2.Chair }}<br>
                {% if session2.Papers and session2.Papers != empty %}
                  <ul class="mb-0">
                    {% for paper in session2.Papers %}
                      <li>
                        {% if paper.URL %}
                          <a href="{{ paper.URL }}" target="_blank" class="custom-link">{{ paper.Title }}</a>
                        {% else %}
                          {{ paper.Title }}
                        {% endif %}
                         <div class="text-muted small">{{ paper.Author }}</div>
                        {% if paper.Comment %}
                          <div class="text-muted small">{{ paper.Comment }}</div>
                        {% endif %}
                      </li>
                    {% endfor %}
                  </ul>
                {% else %}
                  <em>No papers for this session</em>
                {% endif %}
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
          <th style="background-color: #000;">Session 1</th>
          <th style="background-color: #000;">Session 2</th>
        </tr>
      </thead>
      <tbody>
        {% for row in site.data.day2 %}
          {% assign session1 = row.Session1 %}
          {% assign session2 = row.Session2 %}

        {% if row.Keynote %}
        <tr>
            <td>{{ row.Time }}</td>
            <td colspan="2">
            <strong>Keynote:</strong>
            {% if row.Keynote.URL %}
                <a href="{{ row.Keynote.URL }}" target="_blank">{{ row.Keynote.Title }}</a>
            {% else %}
                {{ row.Keynote.Title }}
            {% endif %}
            <br><em>{{ row.Keynote.Author }}</em>
            </td>
        </tr>
        {% elsif row.Lunch %}
            <tr>
              <td>{{ row.Time }}</td>
              <td colspan="2" class="text-center"><strong>{{ row.Lunch.Comment }}</strong></td>
            </tr>
        {% elsif row.Session1.Session == "Best Papers"%}
            <tr>
              <td>{{ row.Time }}</td>
              <td colspan="2">
                <strong>Session: {{ session1.Session }}</strong><br>
                Chair: {{ session1.Chair }}<br>
                {% if session1.Papers and session1.Papers != empty %}
                  <ul class="mb-0">
                    {% for paper in session1.Papers %}
                      <li>
                        {% if paper.URL %}
                          <a href="{{ paper.URL }}" target="_blank" class="custom-link">{{ paper.Title }}</a>
                        {% else %}
                          {{ paper.Title }}
                        {% endif %}
                         <div class="text-muted small">{{ paper.Author }}</div>
                        {% if paper.Comment %}
                          <div class="text-muted small">{{ paper.Comment }}</div>
                        {% endif %}
                      </li>
                    {% endfor %}
                  </ul>
                {% else %}
                  <em>No papers for this session</em>
                {% endif %}
              </td>
            </tr>
          {% else %}
            <tr>
              <td>{{ row.Time }}</td>
  
              <!-- Session 1 -->
              <td>
                <strong>Session: {{ session1.Session }}</strong><br>
                Chair: {{ session1.Chair }}<br>
                {% if session1.Papers and session1.Papers != empty %}
                  <ul class="mb-0">
                    {% for paper in session1.Papers %}
                      <li>
                        {% if paper.URL %}
                          <a href="{{ paper.URL }}" target="_blank" class="custom-link">{{ paper.Title }}</a>
                        {% else %}
                          {{ paper.Title }}
                        {% endif %}
                         <div class="text-muted small">{{ paper.Author }}</div>
                        {% if paper.Comment %}
                          <div class="text-muted small">{{ paper.Comment }}</div>
                        {% endif %}
                      </li>
                    {% endfor %}
                  </ul>
                {% else %}
                  <em>No papers for this session</em>
                {% endif %}
              </td>
  
              <!-- Session 2 -->
              <td>
                <strong>Session: {{ session2.Session }}</strong><br>
                Chair: {{ session2.Chair }}<br>
                {% if session2.Papers and session2.Papers != empty %}
                  <ul class="mb-0">
                    {% for paper in session2.Papers %}
                      <li>
                        {% if paper.URL %}
                          <a href="{{ paper.URL }}" target="_blank" class="custom-link">{{ paper.Title }}</a>
                        {% else %}
                          {{ paper.Title }}
                        {% endif %}
                         <div class="text-muted small">{{ paper.Author }}</div>
                        {% if paper.Comment %}
                          <div class="text-muted small">{{ paper.Comment }}</div>
                        {% endif %}
                      </li>
                    {% endfor %}
                  </ul>
                {% else %}
                  <em>No papers for this session</em>
                {% endif %}
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
          <th style="background-color: #000;">Session 1</th>
          <th style="background-color: #000;">Session 2</th>
        </tr>
      </thead>
      <tbody>
        {% for row in site.data.day3 %}
          {% assign session1 = row.Session1 %}
          {% assign session2 = row.Session2 %}

        {% if row.Keynote %}
        <tr>
            <td>{{ row.Time }}</td>
            <td colspan="2">
            <strong>Keynote:</strong>
            {% if row.Keynote.URL %}
                <a href="{{ row.Keynote.URL }}" target="_blank">{{ row.Keynote.Title }}</a>
            {% else %}
                {{ row.Keynote.Title }}
            {% endif %}
            <br><em>{{ row.Keynote.Author }}</em>
            </td>
        </tr>
        {% elsif row.Lunch %}
            <tr>
              <td>{{ row.Time }}</td>
              <td colspan="2" class="text-center"><strong>{{ row.Lunch.Comment }}</strong></td>
            </tr>
          {% else %}
            <tr>
              <td>{{ row.Time }}</td>
  
              <!-- Session 1 -->
              <td>
                <strong>Session: {{ session1.Session }}</strong><br>
                Chair: {{ session1.Chair }}<br>
                {% if session1.Papers and session1.Papers != empty %}
                  <ul class="mb-0">
                    {% for paper in session1.Papers %}
                      <li>
                        {% if paper.URL %}
                          <a href="{{ paper.URL }}" target="_blank" class="custom-link">{{ paper.Title }}</a>
                        {% else %}
                          {{ paper.Title }}
                        {% endif %}
                         <div class="text-muted small">{{ paper.Author }}</div>
                        {% if paper.Comment %}
                          <div class="text-muted small">{{ paper.Comment }}</div>
                        {% endif %}
                      </li>
                    {% endfor %}
                  </ul>
                {% else %}
                  <em>No papers for this session</em>
                {% endif %}
              </td>
  
              <!-- Session 2 -->
              <td>
                <strong>Session: {{ session2.Session }}</strong><br>
                Chair: {{ session2.Chair }}<br>
                {% if session2.Papers and session2.Papers != empty %}
                  <ul class="mb-0">
                    {% for paper in session2.Papers %}
                      <li>
                        {% if paper.URL %}
                          <a href="{{ paper.URL }}" target="_blank" class="custom-link">{{ paper.Title }}</a>
                        {% else %}
                          {{ paper.Title }}
                        {% endif %}
                         <div class="text-muted small">{{ paper.Author }}</div>
                        {% if paper.Comment %}
                          <div class="text-muted small">{{ paper.Comment }}</div>
                        {% endif %}
                      </li>
                    {% endfor %}
                  </ul>
                {% else %}
                  <em>No papers for this session</em>
                {% endif %}
              </td>
            </tr>
          {% endif %}
        {% endfor %}
      </tbody>
    </table>
  </div>