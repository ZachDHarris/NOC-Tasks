<div id="hb-mini" style="width:299px;height:450px;overflow:hidden;">
<style>
  #hb-mini {
    --hb-bg: #0F1319;
    --hb-panel: #171D26;
    --hb-border: #262F3B;
    --hb-text: #E7ECF2;
    --hb-text-dim: #8993A3;
    --hb-text-faint: #5B6472;
    --hb-day: #E8A33D;
    --hb-evening: #35C3CC;
    --hb-night: #9088F2;
    box-sizing: border-box;
    background: var(--hb-bg);
    color: var(--hb-text);
    font-family: "Inter", -apple-system, BlinkMacSystemFont, sans-serif;
    display: flex;
    flex-direction: column;
    padding: 10px;
    border-radius: 8px;
  }
  #hb-mini * { box-sizing: border-box; }
  #hb-mini .hb-eyebrow {
    font-family: "IBM Plex Mono", monospace;
    font-size: 9px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--hb-text-faint);
    margin: 0 0 4px;
  }
  #hb-mini .hb-daynav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: var(--hb-panel);
    border: 1px solid var(--hb-border);
    border-radius: 6px;
    padding: 6px 8px;
    margin-bottom: 8px;
  }
  #hb-mini .hb-daynav button {
    background: none;
    border: none;
    color: var(--hb-text-dim);
    font-size: 14px;
    cursor: pointer;
    padding: 0 6px;
    line-height: 1;
  }
  #hb-mini .hb-daynav button:hover { color: var(--hb-text); }
  #hb-mini .hb-daylabel {
    font-family: "Oswald", sans-serif;
    font-weight: 600;
    font-size: 14px;
    text-transform: uppercase;
    letter-spacing: 0.02em;
  }
  #hb-mini .hb-daylabel .hb-today-tag {
    font-family: "IBM Plex Mono", monospace;
    font-size: 8px;
    color: var(--hb-night);
    margin-left: 5px;
    letter-spacing: 0.05em;
  }
  #hb-mini .hb-cards {
    display: flex;
    flex-direction: column;
    gap: 6px;
    overflow-y: auto;
    flex: 1;
  }
  #hb-mini .hb-card {
    background: var(--hb-panel);
    border: 1px solid var(--hb-border);
    border-left: 3px solid var(--hb-c, var(--hb-text-faint));
    border-radius: 6px;
    padding: 7px 9px;
  }
  #hb-mini .hb-card.day { --hb-c: var(--hb-day); }
  #hb-mini .hb-card.evening { --hb-c: var(--hb-evening); }
  #hb-mini .hb-card.night { --hb-c: var(--hb-night); }
  #hb-mini .hb-card-head {
    display: flex;
    align-items: baseline;
    gap: 5px;
    margin-bottom: 4px;
  }
  #hb-mini .hb-dot {
    width: 6px; height: 6px; border-radius: 50%;
    background: var(--hb-c, var(--hb-text-faint));
    flex-shrink: 0;
  }
  #hb-mini .hb-card-head h3 {
    font-family: "Oswald", sans-serif;
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 0.02em;
    margin: 0;
    flex: 1;
  }
  #hb-mini .hb-hours {
    font-family: "IBM Plex Mono", monospace;
    font-size: 8.5px;
    color: var(--hb-text-faint);
  }
  #hb-mini .hb-row {
    display: flex;
    justify-content: space-between;
    font-size: 11px;
    padding: 2px 0;
  }
  #hb-mini .hb-task { color: var(--hb-text-dim); }
  #hb-mini .hb-name { font-weight: 600; text-align: right; }
</style>

<p class="hb-eyebrow">Tickets In Progress — Handoff</p>
<div class="hb-daynav">
  <button id="hb-prev" aria-label="Previous day">‹</button>
  <span class="hb-daylabel" id="hb-daylabel">—</span>
  <button id="hb-next" aria-label="Next day">›</button>
</div>
<div class="hb-cards" id="hb-cards"></div>

<script>
(function () {
  var root = document.getElementById("hb-mini");
  var DAYS = ["Sunday","Monday","Tuesday","Wednesday","Thursday","Friday","Saturday"];
  var TASKS = ["Alerts","Chats","Emails & Tickets"];
  var SCHEDULE = [
    { id:"day", label:"Day Shift", hours:"7am–6pm", rows:{
      "Alerts":["Luis","Matt","Sal","Luis","Jason","John","OT"],
      "Chats":["Matt","Sal","Luis","Matt / Jason","John","OT","Jason"],
      "Emails & Tickets":["Sal","Luis","Matt","All","OT","Jason","John"]
    }},
    { id:"evening", label:"Evening Shift", hours:"12pm–11pm", rows:{
      "Alerts":["Middlebrook","Mario","Middlebrook","Mario / Mason","Mason","Mason","Mason"],
      "Chats":["Mario","Middlebrook","Mario","Middlebrook","Mason","Mason","Mason"],
      "Emails & Tickets":["Both","Both","Both","All","Mason","Mason","Mason"]
    }},
    { id:"night", label:"Night Shift", hours:"9pm–8am", rows:{
      "Alerts":["Erika","Brionna","Erika","Ramon / Erika","Vin","Ramon","Vin"],
      "Chats":["Brionna","Erika","Brionna","Brionna / Vin","Ramon","Vin","Ramon"],
      "Emails & Tickets":["Both","Both","Both","Brionna / Vin","Ramon","Vin","Ramon"]
    }}
  ];

  var todayIdx = new Date().getDay();
  var viewIdx = todayIdx;

  function render() {
    root.querySelector("#hb-daylabel").innerHTML =
      DAYS[viewIdx] + (viewIdx === todayIdx ? '<span class="hb-today-tag">TODAY</span>' : "");

    var cards = root.querySelector("#hb-cards");
    cards.innerHTML = "";
    SCHEDULE.forEach(function (shift) {
      var card = document.createElement("div");
      card.className = "hb-card " + shift.id;
      var rowsHtml = TASKS.map(function (task) {
        return '<div class="hb-row"><span class="hb-task">' + task +
          '</span><span class="hb-name">' + shift.rows[task][viewIdx] + "</span></div>";
      }).join("");
      card.innerHTML =
        '<div class="hb-card-head"><span class="hb-dot"></span><h3>' + shift.label +
        '</h3><span class="hb-hours">' + shift.hours + "</span></div>" + rowsHtml;
      cards.appendChild(card);
    });
  }

  root.querySelector("#hb-prev").addEventListener("click", function () {
    viewIdx = (viewIdx + 6) % 7;
    render();
  });
  root.querySelector("#hb-next").addEventListener("click", function () {
    viewIdx = (viewIdx + 1) % 7;
    render();
  });

  render();
})();
</script>
</div>
