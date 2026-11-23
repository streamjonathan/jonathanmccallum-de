---
title: "Einen Künstler vorschlagen"
slug: suggest-an-artist
---

Ich freue mich riesig, Musiker und Künstler kennenzulernen, die Jesus nachfolgen. Wenn du jemanden kennst, über den ich schreiben, den ich interviewen oder über den ich ein Reaktionsvideo machen soll, sag es mir hier.

Ein Name und ein Link reichen — und ein paar Worte dazu, warum gerade diese Person. Ich lese alles, was ankommt. Vielen Dank.

Kennst du jemanden? Tipp auf das Foto, und das Formular füllt sich von selbst aus — dann schreib noch ein paar Worte dazu, warum gerade diese Person, und schick es ab.

<div class="suggest-carousel" role="list" aria-label="Musiker und Künstler, die du vorschlagen kannst">
{% for artist in suggest_carousel %}
  <button type="button" class="suggest-pick" role="listitem" data-artist="{{ artist.name }}" data-link="{{ artist.profile }}" title="{{ artist.name }} vorschlagen">
    <img src="{{ artist.img }}" alt="{{ artist.name }}" loading="lazy" width="150" height="150">
    <span class="suggest-pick__name">{{ artist.name }}</span>
    <span class="suggest-pick__note">{{ artist.note }}</span>
  </button>
{% endfor %}
</div>

<p class="suggest-carousel__more">Oder schlag unten jemanden Neues vor — jeden, von dem du denkst, dass ich ihn kennen sollte.</p>

Diese Seite ist nicht für Menschen unter 18 Jahren.

<form id="suggest-form" class="suggest-form">
  <label for="suggest-artist">Name des Künstlers</label>
  <input id="suggest-artist" name="artist" type="text" maxlength="200" placeholder="Wen soll ich mir ansehen?" required>

  <label for="suggest-link">Link zum Social-Media-Profil</label>
  <input id="suggest-link" name="link" type="url" maxlength="500" placeholder="https://www.instagram.com/…" required>

  <fieldset class="suggest-kinds">
    <legend>Was soll ich mit dieser Person machen?</legend>
    <label><input type="checkbox" name="kind" value="write"> Über diese Person schreiben</label>
    <label><input type="checkbox" name="kind" value="interview"> Diese Person interviewen</label>
    <label><input type="checkbox" name="kind" value="reaction"> Ein Reaktionsvideo über diese Person machen</label>
  </fieldset>

  <label for="suggest-why">Warum gerade diese Person?</label>
  <textarea id="suggest-why" name="why" rows="3" maxlength="500" placeholder="Ein paar Worte reichen…"></textarea>

  <label for="suggest-name">Dein Name <span class="optional">(optional)</span></label>
  <input id="suggest-name" name="fromName" type="text" maxlength="100" placeholder="Damit ich mich bedanken kann">

  <label for="suggest-from-link">Link zu deinem Social-Media-Profil <span class="optional">(optional)</span></label>
  <input id="suggest-from-link" name="fromLink" type="url" maxlength="500" placeholder="https://www.instagram.com/…">

  <button id="suggest-button" type="button">Vorschlag senden</button>

  <p id="suggest-result" aria-live="polite"></p>
</form>
