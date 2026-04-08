# thehelghtshape
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
<title>S.H.A.P.E. Assessment | The Heights Church</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
:root {
  --navy: #0a374e;
  --blue: #1b9bd4;
  --blue-light: #2db3ef;
  --cream: #f4fafd;
  --white: #ffffff;
  --gray: #6b7280;
  --gray-light: #f3f4f6;
  --border: #e5e7eb;
  --text: #1f2937;
  --shadow: 0 4px 24px rgba(10,55,78,0.10);
}
* { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: 'DM Sans', sans-serif; background: var(--cream); color: var(--text); min-height: 100vh; }

/* HEADER */
.header { background: var(--navy); padding: 0 24px; height: 58px; display: flex; align-items: center; justify-content: space-between; position: sticky; top: 0; z-index: 100; box-shadow: 0 2px 12px rgba(0,0,0,0.2); }
.header-left { display: flex; align-items: center; gap: 10px; }
.header-name { font-family: 'DM Sans', sans-serif; color: white; font-size: 0.9rem; font-weight: 500; }
.header-pill { background: var(--blue); color: white; font-size: 0.7rem; font-weight: 600; letter-spacing: 0.09em; text-transform: uppercase; padding: 5px 12px; border-radius: 20px; white-space: nowrap; }

/* PROGRESS */
.progress-wrap { background: rgba(10,55,78,0.08); height: 4px; }
.progress-bar { height: 4px; background: var(--blue); transition: width 0.4s ease; width: 0%; }

/* CONTAINER */
.container { max-width: 700px; margin: 0 auto; padding: 28px 16px 80px; }

/* STEP DOTS */
.step-dots { display: flex; align-items: center; justify-content: center; gap: 6px; margin-bottom: 22px; }
.step-dot { width: 8px; height: 8px; border-radius: 50%; background: var(--border); transition: all 0.3s; }
.step-dot.active { background: var(--navy); width: 22px; border-radius: 4px; }
.step-dot.done { background: var(--blue); }

/* CARDS */
.card { background: var(--white); border-radius: 14px; padding: 28px 22px; box-shadow: var(--shadow); display: none; }
.card.active { display: block; animation: fadeUp 0.35s ease; }
@keyframes fadeUp { from { opacity:0; transform:translateY(12px); } to { opacity:1; transform:translateY(0); } }

/* WELCOME */
.badge { display: inline-block; background: var(--navy); color: white; font-size: 0.7rem; font-weight: 600; letter-spacing: 0.1em; text-transform: uppercase; padding: 5px 14px; border-radius: 20px; margin-bottom: 16px; }
.main-title { font-family: 'Playfair Display', serif; font-size: 2rem; color: var(--navy); line-height: 1.2; margin-bottom: 12px; }
.main-title span { color: var(--blue); }
.sub-text { font-size: 0.92rem; color: var(--gray); line-height: 1.7; margin-bottom: 22px; }

.shape-grid { display: grid; grid-template-columns: repeat(5,1fr); gap: 7px; margin-bottom: 24px; }
.shape-pill { background: var(--blue); color: white; border-radius: 8px; padding: 10px 4px; text-align: center; }
.shape-pill .letter { font-family: 'Playfair Display', serif; font-size: 1.2rem; display: block; margin-bottom: 3px; }
.shape-pill .word { font-size: 0.58rem; text-transform: uppercase; letter-spacing: 0.06em; opacity: 0.9; line-height: 1.3; }

/* INPUTS */
.field-row { display: grid; grid-template-columns: 1fr; gap: 12px; margin-bottom: 6px; }
@media(min-width:520px){ .field-row { grid-template-columns: 1fr 1fr; } }
.field { display: flex; flex-direction: column; gap: 5px; }
.field label { font-size: 0.83rem; font-weight: 600; color: var(--navy); }
.field input { border: 1.5px solid var(--border); border-radius: 10px; padding: 12px 14px; font-family: 'DM Sans', sans-serif; font-size: 0.92rem; color: var(--text); background: white; transition: border-color 0.15s; }
.field input:focus { outline: none; border-color: var(--blue); }

/* SECTION HEADER */
.sec-label { display: inline-block; background: var(--navy); color: var(--blue); font-family: 'Playfair Display', serif; font-size: 0.95rem; padding: 5px 14px; border-radius: 20px; margin-bottom: 12px; }
.sec-title { font-family: 'Playfair Display', serif; font-size: 1.5rem; color: var(--navy); margin-bottom: 8px; }
.sec-desc { font-size: 0.88rem; color: var(--gray); line-height: 1.6; margin-bottom: 18px; padding-bottom: 16px; border-bottom: 1px solid var(--border); }
.scale-legend { display: flex; flex-wrap: wrap; gap: 4px; margin-bottom: 16px; background: var(--gray-light); padding: 9px 13px; border-radius: 8px; font-size: 0.78rem; color: var(--gray); }
.scale-legend strong { color: var(--navy); }

/* GIFT QUESTIONS */
.gq { padding: 13px 0; border-bottom: 1px solid var(--border); display: flex; flex-wrap: wrap; align-items: flex-start; gap: 8px; }
.gq:last-child { border-bottom: none; }
.qn { font-size: 0.7rem; color: var(--gray); font-weight: 600; min-width: 20px; padding-top: 5px; }
.qt { flex: 1; min-width: 200px; font-size: 0.88rem; line-height: 1.5; padding-top: 2px; }
.qs { width: 100%; display: flex; justify-content: space-between; padding-left: 28px; gap: 4px; }
.qs label { cursor: pointer; flex: 1; display: flex; flex-direction: column; align-items: center; gap: 3px; }
.qs input[type=radio] { display: none; }
.qs .val-label { font-size: 0.65rem; color: var(--gray); }
.dot { width: 42px; height: 42px; border-radius: 10px; border: 2px solid var(--border); display: flex; align-items: center; justify-content: center; font-size: 0.88rem; font-weight: 600; color: var(--gray); transition: all 0.15s; width: 100%; }
.qs input:checked + .dot { background: var(--navy); border-color: var(--navy); color: white; }
.qs label:hover .dot { border-color: var(--blue); color: var(--blue); }

/* CHECKBOXES */
.cb-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 7px; margin-bottom: 16px; }
@media(min-width:520px){ .cb-grid { grid-template-columns: repeat(auto-fill, minmax(160px,1fr)); } }
.cb-item { display: flex; align-items: center; gap: 9px; padding: 9px 11px; border: 1.5px solid var(--border); border-radius: 8px; cursor: pointer; transition: all 0.15s; font-size: 0.84rem; }
.cb-item:hover { border-color: var(--blue); background: #f0f9ff; }
.cb-item input { display: none; }
.cb-box { width: 17px; height: 17px; border: 2px solid var(--border); border-radius: 4px; flex-shrink: 0; display: flex; align-items: center; justify-content: center; transition: all 0.15s; }
.cb-item input:checked ~ .cb-box { background: var(--navy); border-color: var(--navy); }
.cb-item input:checked ~ .cb-box::after { content:'✓'; color:white; font-size:11px; font-weight:700; }
.cb-item input:checked ~ span { color: var(--navy); font-weight: 500; }

/* PERSONALITY */
.p-row-wrap { margin-bottom: 10px; }
.p-row-wrap:last-child { margin-bottom: 0; }
.p-row-label { font-size: 0.7rem; color: var(--gray); text-transform: uppercase; letter-spacing: 0.08em; margin-bottom: 6px; font-weight: 600; }
.p-row { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; padding-bottom: 14px; border-bottom: 1px solid var(--border); }
.p-row-wrap:last-child .p-row { border-bottom: none; padding-bottom: 0; }
.p-left, .p-right { display: none; }
.p-sc { display: contents; }
.p-btn-label { cursor: pointer; display: block; }
.p-btn-label input { display: none; }
.p-btn {
  display: flex; align-items: center; justify-content: center;
  padding: 13px 10px; border-radius: 10px; border: 2px solid var(--border);
  font-size: 0.86rem; color: var(--gray); line-height: 1.4; text-align: center;
  transition: all 0.15s; min-height: 60px; background: white;
}
.p-btn-label input:checked + .p-btn {
  background: var(--navy); border-color: var(--navy); color: white; font-weight: 600;
}
.p-btn-label:hover .p-btn { border-color: var(--blue); color: var(--blue); }
.p-row.unanswered .p-btn { border-color: #fca5a5; background: #fff5f5; }

/* EXPERIENCE */
.exp-group { margin-bottom: 16px; }
.exp-label { font-size: 0.86rem; font-weight: 600; color: var(--navy); margin-bottom: 3px; display: block; }
.exp-sub { font-size: 0.78rem; color: var(--gray); margin-bottom: 7px; display: block; }
textarea { width: 100%; border: 1.5px solid var(--border); border-radius: 10px; padding: 11px 13px; font-family: 'DM Sans', sans-serif; font-size: 0.9rem; color: var(--text); resize: vertical; min-height: 76px; transition: border-color 0.15s; }
textarea:focus { outline: none; border-color: var(--blue); }

/* BUTTONS */
.btn-row { display: flex; flex-direction: column; gap: 10px; padding-top: 20px; border-top: 1px solid var(--border); margin-top: 20px; }
@media(min-width:400px){ .btn-row { flex-direction: row; justify-content: flex-end; } }
.btn-p { background: linear-gradient(135deg, var(--navy), #0d5070); color: white; border: none; padding: 14px 28px; border-radius: 10px; font-family: 'DM Sans', sans-serif; font-size: 0.96rem; font-weight: 600; cursor: pointer; transition: all 0.2s; text-align: center; }
.btn-p:hover { transform: translateY(-1px); box-shadow: 0 5px 16px rgba(10,55,78,0.3); }
.btn-s { background: transparent; color: var(--navy); border: 1.5px solid var(--border); padding: 13px 20px; border-radius: 10px; font-family: 'DM Sans', sans-serif; font-size: 0.91rem; font-weight: 500; cursor: pointer; transition: all 0.2s; text-align: center; }
.btn-s:hover { border-color: var(--navy); }
.err { color: #ef4444; font-size: 0.8rem; margin-top: 8px; }
.divider { border: none; border-top: 1.5px solid var(--border); margin: 20px 0; }
.section-sub { font-size: 0.88rem; color: var(--navy); font-weight: 600; margin-bottom: 10px; }

/* RESULTS */
#results { display: none; }
.r-header { background: linear-gradient(135deg, var(--navy), #0d5070); border-radius: 14px; padding: 32px 24px; color: white; text-align: center; margin-bottom: 18px; }
.r-name { font-family: 'Playfair Display', serif; font-size: 1.8rem; margin-bottom: 5px; }
.r-sub { font-size: 0.86rem; opacity: 0.72; margin-bottom: 18px; }
.shape-tags { display: flex; gap: 7px; justify-content: center; flex-wrap: wrap; }
.s-tag { background: rgba(27,155,212,0.25); border: 1px solid rgba(27,155,212,0.5); color: #90d8f7; padding: 4px 13px; border-radius: 20px; font-size: 0.8rem; font-weight: 500; }

.r-section { background: white; border-radius: 12px; padding: 22px 20px; margin-bottom: 14px; box-shadow: var(--shadow); }
.r-sec-title { display: flex; align-items: center; gap: 9px; font-family: 'Playfair Display', serif; font-size: 1.15rem; color: var(--navy); margin-bottom: 16px; padding-bottom: 12px; border-bottom: 1px solid var(--border); }
.r-icon { width: 32px; height: 32px; background: var(--navy); color: var(--blue); border-radius: 7px; display: flex; align-items: center; justify-content: center; font-family: 'Playfair Display', serif; font-size: 0.9rem; font-weight: 700; flex-shrink: 0; }

.bar-row { display: flex; align-items: center; gap: 10px; margin-bottom: 9px; }
.bar-name { font-size: 0.82rem; font-weight: 500; flex: 1; min-width: 0; }
.bar-wrap { width: 100px; height: 9px; background: var(--gray-light); border-radius: 5px; overflow: hidden; flex-shrink: 0; }
@media(min-width:400px){ .bar-wrap { width: 140px; } }
.bar-fill { height: 100%; border-radius: 5px; background: linear-gradient(90deg, var(--blue), var(--blue-light)); transition: width 1s ease; }
.bar-fill.top { background: linear-gradient(90deg, var(--navy), var(--blue)); }
.bar-score { font-size: 0.78rem; color: var(--gray); min-width: 26px; text-align: right; flex-shrink: 0; }
.top-badge { font-size: 0.6rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.07em; color: var(--blue); background: #e8f6fd; padding: 2px 7px; border-radius: 10px; margin-left: 4px; }

.p-result { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
.p-box { background: var(--gray-light); border-radius: 9px; padding: 13px; }
.p-box-label { font-size: 0.7rem; color: var(--gray); text-transform: uppercase; letter-spacing: 0.08em; margin-bottom: 3px; }
.p-box-val { font-size: 0.98rem; font-weight: 700; color: var(--navy); }
.p-box-desc { font-size: 0.79rem; color: var(--gray); margin-top: 4px; line-height: 1.4; }

.tags { display: flex; flex-wrap: wrap; gap: 7px; }
.tag { background: #e8f6fd; border: 1px solid #b3dff5; color: var(--navy); padding: 5px 12px; border-radius: 20px; font-size: 0.8rem; font-weight: 500; }

.exp-r { margin-bottom: 13px; }
.exp-r-label { font-size: 0.8rem; font-weight: 600; color: var(--navy); margin-bottom: 3px; }
.exp-r-text { font-size: 0.86rem; color: var(--gray); line-height: 1.5; font-style: italic; }

/* MATCH CARDS */
.match-type-label { font-size: 0.74rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.09em; color: var(--blue); margin: 14px 0 9px; }
.match-card { border: 1.5px solid var(--border); border-radius: 10px; padding: 13px 15px; margin-bottom: 9px; background: white; }
.match-card-name { font-weight: 600; color: var(--navy); font-size: 0.91rem; margin-bottom: 4px; }
.match-card-desc { font-size: 0.82rem; color: var(--gray); line-height: 1.5; }
.match-profile { background: var(--gray-light); border-radius: 9px; padding: 14px 16px; margin-bottom: 14px; font-size: 0.88rem; color: var(--text); line-height: 1.6; }
.match-profile strong { color: var(--navy); display: block; margin-bottom: 4px; font-size: 0.84rem; text-transform: uppercase; letter-spacing: 0.05em; }

/* CTA */
.cta { background: linear-gradient(135deg, var(--navy), #0d5070); border-radius: 12px; padding: 24px 22px; text-align: center; margin-bottom: 14px; }
.cta h3 { font-family: 'Playfair Display', serif; color: white; font-size: 1.2rem; margin-bottom: 5px; }
.cta p { color: rgba(255,255,255,0.78); font-size: 0.86rem; margin-bottom: 14px; }
.btn-gold { background: var(--blue); color: white; border: none; padding: 12px 24px; border-radius: 10px; font-family: 'DM Sans', sans-serif; font-size: 0.92rem; font-weight: 600; cursor: pointer; text-decoration: none; display: inline-block; transition: all 0.2s; }
.btn-gold:hover { transform: translateY(-1px); box-shadow: 0 5px 14px rgba(0,0,0,0.25); }

/* EDIT PANEL */
#editToggle { position: fixed; bottom: 14px; right: 14px; z-index: 999; background: rgba(10,55,78,0.35); color: rgba(255,255,255,0.6); border: none; border-radius: 6px; padding: 5px 10px; font-family: 'DM Sans', sans-serif; font-size: 0.68rem; font-weight: 500; cursor: pointer; letter-spacing: 0.04em; transition: all 0.2s; }
#editToggle:hover { background: var(--navy); color: white; }
#editPanel { position: fixed; top: 0; right: -420px; width: min(400px, 100vw); height: 100vh; background: white; z-index: 1000; box-shadow: -4px 0 28px rgba(0,0,0,0.14); transition: right 0.3s ease; overflow-y: auto; }
#editPanel.open { right: 0; }
.ep-overlay { display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.28); z-index: 999; }
.ep-overlay.open { display: block; }
.ep-hdr { background: var(--navy); color: white; padding: 18px 22px; display: flex; align-items: center; justify-content: space-between; }
.ep-hdr h3 { font-family: 'Playfair Display', serif; font-size: 1.05rem; }
.ep-close { background: none; border: none; color: white; font-size: 1.3rem; cursor: pointer; }
.ep-body { padding: 18px 22px; }
.ep-sec-title { font-size: 0.7rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.1em; color: var(--blue); margin: 16px 0 8px; padding-bottom: 5px; border-bottom: 1px solid var(--border); }
.ep-field { margin-bottom: 11px; }
.ep-field label { display: block; font-size: 0.79rem; font-weight: 600; color: var(--navy); margin-bottom: 4px; }
.ep-field input, .ep-field textarea { width: 100%; border: 1.5px solid var(--border); border-radius: 8px; padding: 8px 11px; font-family: 'DM Sans', sans-serif; font-size: 0.84rem; color: var(--text); resize: vertical; }
.ep-field input:focus, .ep-field textarea:focus { outline: none; border-color: var(--blue); }
.ep-apply { width: 100%; background: var(--navy); color: white; border: none; padding: 12px; border-radius: 8px; font-family: 'DM Sans', sans-serif; font-size: 0.91rem; font-weight: 600; cursor: pointer; margin-top: 8px; }
.ep-note { font-size: 0.75rem; color: var(--gray); line-height: 1.5; background: var(--gray-light); padding: 9px 12px; border-radius: 7px; margin-bottom: 4px; }

/* ── PRINT / PDF ── */
@media print {
  * { -webkit-print-color-adjust: exact !important; print-color-adjust: exact !important; color-adjust: exact !important; }

  @page { margin: 12mm 14mm; size: Letter; }

  body { background: white !important; font-family: 'DM Sans', sans-serif; font-size: 11pt; }

  /* Hide everything except results */
  .header, .progress-wrap, #editToggle, #editPanel, .ep-overlay,
  #stepDots, .card, .cta, #results > div:last-child,
  #pwGate, #printBtn { display: none !important; }

  #results { display: block !important; }

  /* Hide screen header, show PDF header */
  .r-header { display: none !important; }
  .pdf-header { display: flex !important; }

  /* Page layout */
  .container { padding: 0 !important; max-width: 100% !important; }

  /* Section cards */
  .r-section {
    box-shadow: none !important;
    border: 1px solid #d1d5db !important;
    border-radius: 8px !important;
    break-inside: avoid;
    margin-bottom: 10pt !important;
    padding: 12pt 14pt !important;
    page-break-inside: avoid;
  }

  .r-sec-title {
    font-size: 11pt !important;
    margin-bottom: 10pt !important;
    padding-bottom: 8pt !important;
  }

  .r-icon {
    width: 24px !important; height: 24px !important;
    font-size: 0.75rem !important;
  }

  /* Gift bars */
  .bar-row { margin-bottom: 7pt !important; }
  .bar-name { font-size: 9pt !important; }
  .bar-wrap { width: 160px !important; height: 8px !important; }
  .bar-score { font-size: 8pt !important; }
  .top-badge { font-size: 7pt !important; padding: 1px 5px !important; }

  /* Tags */
  .tag { font-size: 8pt !important; padding: 3px 9px !important; border: 1px solid #b3dff5 !important; }

  /* Personality */
  .p-result { grid-template-columns: 1fr 1fr !important; gap: 8pt !important; }
  .p-box { padding: 10pt !important; }
  .p-box-val { font-size: 10pt !important; }
  .p-box-desc { font-size: 8pt !important; }

  /* Experience */
  .exp-r { margin-bottom: 8pt !important; }
  .exp-r-label { font-size: 9pt !important; }
  .exp-r-text { font-size: 9pt !important; }

  /* Match cards */
  .match-card { break-inside: avoid; page-break-inside: avoid; margin-bottom: 7pt !important; padding: 9pt 11pt !important; border: 1px solid #d1d5db !important; border-radius: 6px !important; }
  .match-card-name { font-size: 9.5pt !important; }
  .match-card-desc { font-size: 8.5pt !important; }
  .match-type-label { break-after: avoid; page-break-after: avoid; font-size: 8pt !important; margin: 10pt 0 6pt !important; }
  .match-profile { font-size: 8.5pt !important; padding: 10pt !important; break-inside: avoid; }

  /* PDF CTA footer */
  .pdf-cta { display: block !important; }
}

/* PDF header — hidden on screen, shown when printing */
.pdf-header {
  display: none;
  background: #0a374e;
  color: white;
  padding: 14px 20px;
  border-radius: 10px;
  margin-bottom: 14px;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
}
.pdf-header-left h2 {
  font-family: 'Playfair Display', serif;
  font-size: 1.3rem;
  margin-bottom: 2px;
}
.pdf-header-left p { font-size: 0.78rem; opacity: 0.72; margin-bottom: 6px; }
.pdf-header-shape { display: flex; gap: 5px; flex-wrap: wrap; }
.pdf-s-tag {
  background: rgba(27,155,212,0.3);
  border: 1px solid rgba(27,155,212,0.5);
  color: #90d8f7;
  padding: 3px 9px; border-radius: 12px; font-size: 0.7rem; font-weight: 500;
}
.pdf-header-right {
  text-align: right; flex-shrink: 0;
}
.pdf-header-right .pdf-logo-text {
  font-family: 'Playfair Display', serif;
  font-size: 1.6rem; font-weight: 700; color: #1b9bd4; display: block;
}
.pdf-header-right .pdf-site {
  font-size: 0.72rem; opacity: 0.65;
}
.pdf-header-right .pdf-date {
  font-size: 0.7rem; opacity: 0.55; margin-top: 2px;
}
.pdf-cta {
  display: none;
  background: #f4fafd;
  border: 1px solid #b3dff5;
  border-radius: 8px;
  padding: 11px 16px;
  margin-top: 10px;
}
.pdf-cta p { font-size: 0.82rem; color: #0a374e; line-height: 1.6; }
.pdf-cta strong { display: block; margin-bottom: 3px; font-size: 0.78rem; text-transform: uppercase; letter-spacing: 0.05em; }

/* Print button */
#printBtn {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  background: white;
  color: var(--navy);
  border: 2px solid var(--navy);
  padding: 12px 24px;
  border-radius: 10px;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.93rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s;
  margin: 0 auto 14px;
  width: 100%;
  max-width: 280px;
}
#printBtn:hover { background: var(--navy); color: white; }

/* PDF-specific header (hidden on screen) */
.pdf-header {
  display: none;
  background: #0a374e;
  color: white;
  padding: 18px 24px;
  border-radius: 10px;
  margin-bottom: 14px;
  align-items: center;
  justify-content: space-between;
}
.pdf-header-left h2 { font-family: 'Playfair Display', serif; font-size: 1.4rem; margin-bottom: 2px; }
.pdf-header-left p { font-size: 0.8rem; opacity: 0.75; }
.pdf-header-right { text-align: right; font-size: 0.78rem; opacity: 0.75; }
.pdf-header-shape { display: flex; gap: 6px; flex-wrap: wrap; margin-top: 8px; }
.pdf-s-tag { background: rgba(27,155,212,0.3); border: 1px solid rgba(27,155,212,0.5); color: #90d8f7; padding: 3px 10px; border-radius: 12px; font-size: 0.72rem; }
.pdf-cta { display: none; background: #f4fafd; border: 1px solid #b3dff5; border-radius: 8px; padding: 12px 16px; margin-top: 10px; }
.pdf-cta p { font-size: 0.82rem; color: #0a374e; }
.pdf-cta strong { display: block; margin-bottom: 3px; }

/* Print button */
#printBtn {
  display: flex;
  align-items: center;
  gap: 8px;
  background: white;
  color: #0a374e;
  border: 2px solid #0a374e;
  padding: 11px 22px;
  border-radius: 10px;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.92rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s;
  margin: 0 auto 14px;
}
#printBtn:hover { background: #0a374e; color: white; }
</style>
</head>
<body>

<div class="header">
  <div class="header-left">
    <span class="header-name">The Heights Church</span>
  </div>
  <div class="header-pill">S.H.A.P.E. Assessment</div>
</div>
<div class="progress-wrap"><div class="progress-bar" id="progressBar"></div></div>

<div class="container">
  <div class="step-dots" id="stepDots"></div>

  <!-- WELCOME -->
  <div class="card active" id="step-0">
    <div class="badge">Discover Your Calling</div>
    <h1 class="main-title">God shaped you<br><span>on purpose.</span></h1>
    <p class="sub-text">This short assessment (about 10 minutes) helps you discover how God has uniquely designed you to serve. There are no right or wrong answers — just honest ones.</p>
    <div class="shape-grid">
      <div class="shape-pill"><span class="letter">S</span><span class="word">Spiritual Gifts</span></div>
      <div class="shape-pill"><span class="letter">H</span><span class="word">Heart & Passion</span></div>
      <div class="shape-pill"><span class="letter">A</span><span class="word">Abilities</span></div>
      <div class="shape-pill"><span class="letter">P</span><span class="word">Personality</span></div>
      <div class="shape-pill"><span class="letter">E</span><span class="word">Experiences</span></div>
    </div>
    <div class="field-row">
      <div class="field"><label>First Name *</label><input type="text" id="firstName" placeholder="First name"></div>
      <div class="field"><label>Last Name *</label><input type="text" id="lastName" placeholder="Last name"></div>
      <div class="field"><label>Email Address *</label><input type="email" id="email" placeholder="your@email.com"></div>
      <div class="field"><label>Phone (optional)</label><input type="tel" id="phone" placeholder="(555) 000-0000"></div>
    </div>
    <div class="err" id="err-0"></div>
    <div style="margin-top:16px;">
      <button class="btn-p" id="beginBtn">Begin Assessment →</button>
    </div>
    <p style="font-size:0.72rem;color:var(--gray);margin-top:16px;line-height:1.5;">S.H.A.P.E. framework originally developed by Rick Warren, Saddleback Church.</p>
  </div>

  <!-- SPIRITUAL GIFTS -->
  <div class="card" id="step-1">
    <div class="sec-label">S — Spiritual Gifts</div>
    <h2 class="sec-title">What has God supernaturally gifted you to do?</h2>
    <p class="sec-desc">Answer honestly about who you are, not who you think you should be.</p>
    <div class="scale-legend">
      <strong>3</strong>&nbsp;= Consistently true &nbsp;|&nbsp;
      <strong>2</strong>&nbsp;= Usually true &nbsp;|&nbsp;
      <strong>1</strong>&nbsp;= Sometimes &nbsp;|&nbsp;
      <strong>0</strong>&nbsp;= Not at all
    </div>
    <div id="giftQs"></div>
    <div class="err" id="err-1"></div>
    <div class="btn-row">
      <button class="btn-s" id="back1">← Back</button>
      <button class="btn-p" id="next1">Continue →</button>
    </div>
  </div>

  <!-- HEART -->
  <div class="card" id="step-2">
    <div class="sec-label">H — Heart</div>
    <h2 class="sec-title">What drives you?</h2>
    <p class="sec-desc">"Delight yourself in the LORD and he will give you the desires of your heart." — Psalm 37:4</p>
    <p class="section-sub">People I most want to serve:</p>
    <div class="cb-grid" id="heartPeople"></div>
    <hr class="divider">
    <p class="section-sub">Causes I feel strongly about:</p>
    <div class="cb-grid" id="heartCauses"></div>
    <div class="btn-row">
      <button class="btn-s" id="back2">← Back</button>
      <button class="btn-p" id="next2">Continue →</button>
    </div>
  </div>

  <!-- ABILITIES -->
  <div class="card" id="step-3">
    <div class="sec-label">A — Abilities</div>
    <h2 class="sec-title">What are you naturally good at?</h2>
    <p class="sec-desc">Check everything you genuinely excel at — things that come naturally, whether or not you've used them in ministry before.</p>
    <div class="cb-grid" id="abilitiesList"></div>
    <div class="btn-row">
      <button class="btn-s" id="back3">← Back</button>
      <button class="btn-p" id="next3">Continue →</button>
    </div>
  </div>

  <!-- PERSONALITY -->
  <div class="card" id="step-4">
    <div class="sec-label">P — Personality</div>
    <h2 class="sec-title">How has God wired you?</h2>
    <p class="sec-desc">For each row, tap the statement that sounds most like you. <strong style="color:var(--navy)">You must select one from each row</strong> before moving on. Go with your first instinct — there are no right or wrong answers.</p>
    <p class="section-sub" style="margin-bottom:12px;">How are you energized?</p>
    <div id="energyRows"></div>
    <hr class="divider">
    <p class="section-sub" style="margin-bottom:12px;">How are you organized?</p>
    <div id="organizeRows"></div>
    <div class="err" id="err-4"></div>
    <div class="btn-row">
      <button class="btn-s" id="back4">← Back</button>
      <button class="btn-p" id="next4">Continue →</button>
    </div>
  </div>

  <!-- EXPERIENCE -->
  <div class="card" id="step-5">
    <div class="sec-label">E — Experiences</div>
    <h2 class="sec-title">What has God brought you through?</h2>
    <p class="sec-desc">"God comforts us in all our troubles, so that we can comfort those in any trouble." — 2 Corinthians 1:3–4</p>
    <div class="exp-group">
      <span class="exp-label">Spiritual Experiences</span>
      <span class="exp-sub">Turning points in your faith, times you felt especially close to God.</span>
      <textarea id="expSpiritual" placeholder="Share as little or as much as you'd like..."></textarea>
    </div>
    <div class="exp-group">
      <span class="exp-label">Painful Experiences</span>
      <span class="exp-sub">Trials or hard seasons God has used or is using in your life.</span>
      <textarea id="expPainful" placeholder="Share as little or as much as you'd like..."></textarea>
    </div>
    <div class="exp-group">
      <span class="exp-label">Education & Work Background</span>
      <span class="exp-sub">Degrees, training, career experience, skills you've developed.</span>
      <textarea id="expEducation" placeholder="e.g., degree in education, 10 years in healthcare..."></textarea>
    </div>
    <div class="exp-group">
      <span class="exp-label">Ministry Experience</span>
      <span class="exp-sub">How you've served before — formally or informally, inside or outside the church.</span>
      <textarea id="expMinistry" placeholder="e.g., small group leader, VBS volunteer, worship team..."></textarea>
    </div>
    <div class="btn-row">
      <button class="btn-s" id="back5">← Back</button>
      <button class="btn-p" id="submitBtn">See My Results →</button>
    </div>
  </div>

  <!-- RESULTS -->
  <div id="results">
    <!-- PDF-only header -->
    <div class="pdf-header" id="pdfHeader">
      <div class="pdf-header-left">
        <h2 id="pdfName"></h2>
        <p>S.H.A.P.E. Assessment Results &nbsp;|&nbsp; The Heights Church</p>
        <div class="pdf-header-shape" id="pdfTags"></div>
      </div>
      <div class="pdf-header-right">
        <span class="pdf-logo-text">S.H.A.P.E.</span>
        <div class="pdf-site">theheights.org</div>
        <div class="pdf-date" id="pdfDate"></div>
      </div>
    </div>
    <div class="r-header">
      <div class="r-name" id="rName"></div>
      <div class="r-sub">Here's how God has uniquely shaped you to serve.</div>
      <div class="shape-tags" id="shapeTags"></div>
    </div>
    <div class="r-section">
      <div class="r-sec-title"><div class="r-icon">S</div>Spiritual Gifts</div>
      <div id="giftBars"></div>
    </div>
    <div class="r-section">
      <div class="r-sec-title"><div class="r-icon">H</div>Heart & Passion</div>
      <div style="font-size:.74rem;color:var(--gray);font-weight:600;text-transform:uppercase;letter-spacing:.07em;margin-bottom:7px;">People</div>
      <div class="tags" id="rPeople" style="margin-bottom:14px;"></div>
      <div style="font-size:.74rem;color:var(--gray);font-weight:600;text-transform:uppercase;letter-spacing:.07em;margin-bottom:7px;">Causes</div>
      <div class="tags" id="rCauses"></div>
    </div>
    <div class="r-section">
      <div class="r-sec-title"><div class="r-icon">A</div>Abilities</div>
      <div class="tags" id="rAbilities"></div>
    </div>
    <div class="r-section">
      <div class="r-sec-title"><div class="r-icon">P</div>Personality</div>
      <div class="p-result">
        <div class="p-box"><div class="p-box-label">Energy Style</div><div class="p-box-val" id="rEnergyVal"></div><div class="p-box-desc" id="rEnergyDesc"></div></div>
        <div class="p-box"><div class="p-box-label">Organization Style</div><div class="p-box-val" id="rOrgVal"></div><div class="p-box-desc" id="rOrgDesc"></div></div>
      </div>
    </div>
    <div class="r-section">
      <div class="r-sec-title"><div class="r-icon">E</div>Experiences</div>
      <div id="rExp"></div>
    </div>
    <div class="r-section">
      <div class="r-sec-title"><div class="r-icon">✦</div>Suggested Serving Areas</div>
      <div id="rMatches"></div>
    </div>
    <button id="printBtn" onclick="window.print()">🖨️ Print / Save as PDF</button>
    <!-- PDF-only CTA -->
    <div class="pdf-cta">
      <p><strong>Next Steps</strong>A member of our team will reach out to help connect your SHAPE to a serving opportunity at The Heights. Questions? Email <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="b2c1d7c0c4d7f2c6dad7dad7dbd5dac6c19cddc0d5">[email&#160;protected]</a> or visit theheights.org/serve</p>
    </div>
    <div class="cta">
      <h3>Ready to find your place?</h3>
      <p>A member of our team will reach out to help connect your SHAPE to a serving opportunity at The Heights.</p>
      <a href="https://www.theheights.org/about-us/serve/" class="btn-gold">Explore Serving Opportunities</a>
    </div>
    <div style="text-align:center;padding:12px 0 6px;color:var(--gray);font-size:0.79rem;">
      Questions? Contact us at <strong><a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="82f1e7f0f4e7c2f6eae7eae7ebe5eaf6f1acedf0e5">[email&#160;protected]</a></strong>
    </div>
  </div>
</div>

<!-- EDIT PANEL -->
<div class="ep-overlay" id="epOverlay"></div>
<button id="editToggle">Admin</button>

<!-- Password Gate -->
<div id="pwGate" style="display:none;position:fixed;inset:0;background:rgba(0,0,0,0.5);z-index:1001;align-items:center;justify-content:center;">
  <div style="background:white;border-radius:14px;padding:32px;width:min(340px,90vw);box-shadow:0 8px 32px rgba(0,0,0,0.2);">
    <h3 style="font-family:'Playfair Display',serif;color:var(--navy);margin-bottom:6px;">Staff Access</h3>
    <p style="font-size:0.84rem;color:var(--gray);margin-bottom:16px;">Enter the staff password to edit page content.</p>
    <input type="password" id="pwInput" placeholder="Password" style="width:100%;border:1.5px solid var(--border);border-radius:8px;padding:11px 13px;font-family:'DM Sans',sans-serif;font-size:0.92rem;margin-bottom:8px;">
    <div id="pwError" style="color:#ef4444;font-size:0.8rem;margin-bottom:10px;min-height:16px;"></div>
    <div style="display:flex;gap:10px;">
      <button id="pwCancel" style="flex:1;padding:11px;border:1.5px solid var(--border);border-radius:8px;background:transparent;font-family:'DM Sans',sans-serif;font-size:0.9rem;cursor:pointer;">Cancel</button>
      <button id="pwSubmit" style="flex:1;padding:11px;background:var(--navy);color:white;border:none;border-radius:8px;font-family:'DM Sans',sans-serif;font-size:0.9rem;font-weight:600;cursor:pointer;">Enter</button>
    </div>
  </div>
</div>

<div id="editPanel">
  <div class="ep-hdr"><h3>Edit Content</h3><button class="ep-close" id="epClose">✕</button></div>
  <div class="ep-body">
    <p class="ep-note">Changes apply instantly to this session. Send updated text to your developer to make them permanent.</p>

    <div class="ep-sec-title">Welcome Screen</div>
    <div class="ep-field"><label>Headline line 1</label><input type="text" id="ep_t1" value="God shaped you"></div>
    <div class="ep-field"><label>Headline line 2</label><input type="text" id="ep_t2" value="on purpose."></div>
    <div class="ep-field"><label>Subtitle</label><textarea id="ep_sub" rows="3">This short assessment (about 10 minutes) helps you discover how God has uniquely designed you to serve. There are no right or wrong answers — just honest ones.</textarea></div>

    <div class="ep-sec-title">Spiritual Gifts (S)</div>
    <div class="ep-field"><label>Section description</label><textarea id="ep_sdesc" rows="2">Answer honestly about who you are, not who you think you should be.</textarea></div>

    <div class="ep-sec-title">Heart (H)</div>
    <div class="ep-field"><label>Section description</label><textarea id="ep_hdesc" rows="2">"Delight yourself in the LORD and he will give you the desires of your heart." — Psalm 37:4</textarea></div>

    <div class="ep-sec-title">Abilities (A)</div>
    <div class="ep-field"><label>Section description</label><textarea id="ep_adesc" rows="2">Check everything you genuinely excel at — things that come naturally, whether or not you've used them in ministry before.</textarea></div>

    <div class="ep-sec-title">Personality (P)</div>
    <div class="ep-field"><label>Section description</label><textarea id="ep_pdesc" rows="2">For each pair below, tap the statement that sounds most like you. Go with your first instinct — there are no right or wrong answers.</textarea></div>

    <div class="ep-sec-title">Experience (E)</div>
    <div class="ep-field"><label>Section description</label><textarea id="ep_edesc" rows="2">"God comforts us in all our troubles, so that we can comfort those in any trouble." — 2 Corinthians 1:3–4</textarea></div>

    <div class="ep-sec-title">Results Page</div>
    <div class="ep-field"><label>Results subtitle</label><input type="text" id="ep_rsub" value="Here's how God has uniquely shaped you to serve."></div>
    <div class="ep-field"><label>CTA headline</label><input type="text" id="ep_ctaH" value="Ready to find your place?"></div>
    <div class="ep-field"><label>CTA body text</label><textarea id="ep_ctaB" rows="2">A member of our team will reach out to help connect your SHAPE to a serving opportunity at The Heights.</textarea></div>
    <div class="ep-field"><label>CTA button text</label><input type="text" id="ep_ctaBtn" value="Explore Serving Opportunities"></div>
    <div class="ep-field"><label>Contact email</label><input type="text" id="ep_email" value="serve" + "@" + "theheights.org"></div>

    <button class="ep-apply" id="epApply">Apply Changes</button>
  </div>
</div>

<script data-cfasync="false">
// ── DATA ──────────────────────────────────────────────────────────

var giftQs = [
  { text: "I like to organize people, tasks, and events — others come to me to get things coordinated.", gift: "Administration" },
  { text: "I communicate the gospel clearly and feel genuinely drawn to share my faith with those who don't know Jesus.", gift: "Evangelism" },
  { text: "I find it natural to trust God in situations where others struggle, even when outcomes are uncertain.", gift: "Faith" },
  { text: "I'm drawn to people who are hurting and feel compelled to come alongside them in their healing.", gift: "Mercy" },
  { text: "I can motivate and influence others to move toward a vision — people follow my lead.", gift: "Leadership" },
  { text: "I can explain Scripture in ways that help people understand and apply it to their everyday lives.", gift: "Teaching" },
  { text: "I give generously — money, time, resources — because I believe it advances God's work in real ways.", gift: "Giving" },
  { text: "I enjoy praying for others at length and often sense specific things God wants me to pray for.", gift: "Intercession" },
  { text: "I can sense when something is spiritually off — in a teaching, a situation, or a person's character.", gift: "Discernment" },
  { text: "I naturally encourage and strengthen people who are discouraged, wavering, or in need of hope.", gift: "Encouragement" }
];

var heartPeopleOpts = ["Children","Youth","College Students","Young Married Couples","Men","Women","Elderly","Disabled","Homeless","Divorced / Single Parents","Those in Recovery","Internationals / Immigrants"];
var heartCausesOpts = ["Marriage & Family","At-risk Children","Poverty & Hunger","Spiritual Apathy","Mental Health","Addiction & Recovery","Education","Racial Reconciliation","Missions & Church Planting","Care for the Elderly","Evangelism & Outreach","Discipleship"];
var abilitiesOpts   = ["Administrating","Analyzing","Building / Craftsmanship","Coaching","Communicating","Computing / Tech","Connecting People","Counseling","Creating / Designing","Decorating","Directing / Managing","Encouraging","Facilitating","Leading","Mentoring","Organizing","Performing (music, drama, etc.)","Planning","Teaching / Training","Welcoming / Hospitality","Writing"];

var energyPairs = [
  ["I'm energized by accomplishing tasks","I'm energized by building relationships"],
  ["I focus on what needs to get done","I focus on who is in the room"],
  ["I'd rather start a meeting on time","I'd rather start when everyone feels connected"],
  ["I place higher value on action","I place higher value on communication"]
];
var orgPairs = [
  ["I prefer to stay flexible and spontaneous","I prefer to follow a clear plan"],
  ["I like to keep my options open","I like to settle things and move forward"],
  ["I find routine boring","I find routine restful and helpful"]
];

var servingTeams = [
  { name:"Guest Connections Welcome Team", type:"inside", desc:"You're often the first face someone sees. This team creates belonging from the moment people walk in.", gifts:["Hospitality","Evangelism","Encouragement"], abilities:["Welcoming / Hospitality","Connecting People","Communicating"], people:["Children","Youth","Men","Women","Internationals / Immigrants"], causes:["Evangelism & Outreach","Spiritual Apathy"], energy:"People-Oriented" },
  { name:"Worship Team", type:"inside", desc:"Lead people into the presence of God through music, creativity, and artistic gifts.", gifts:["Creative Communication","Encouragement"], abilities:["Performing (music, drama, etc.)","Creating / Designing"], people:[], causes:["Discipleship"], energy:null },
  { name:"Media / Production", type:"inside", desc:"Behind the scenes but essential — you make sure everything looks and sounds excellent on Sunday.", gifts:["Helps","Administration"], abilities:["Computing / Tech","Creating / Designing","Planning"], people:[], causes:[], energy:"Task-Oriented" },
  { name:"Care Ministries", type:"inside", desc:"Walk alongside people in their hardest seasons — grief, illness, crisis, and loss.", gifts:["Mercy","Shepherding","Intercession"], abilities:["Counseling","Encouraging","Connecting People"], people:["Elderly","Disabled","Divorced / Single Parents","Those in Recovery"], causes:["Mental Health","Marriage & Family","Care for the Elderly"], energy:"People-Oriented" },
  { name:"Preschool (Birth–Kinder)", type:"inside", desc:"Lay the earliest foundation of faith in the lives of our youngest kids and their families.", gifts:["Mercy","Hospitality","Teaching","Encouragement"], abilities:["Teaching / Training","Encouraging","Welcoming / Hospitality"], people:["Children"], causes:["Marriage & Family"], energy:"People-Oriented" },
  { name:"Kids Ministry (K–6th Grade)", type:"inside", desc:"Teach, shepherd, and invest in the spiritual lives of elementary-age kids every week.", gifts:["Teaching","Encouragement","Shepherding"], abilities:["Teaching / Training","Coaching","Encouraging"], people:["Children"], causes:["Discipleship","Education"], energy:"People-Oriented" },
  { name:"Students (7th–12th Grade)", type:"inside", desc:"Journey with teenagers through some of the most formative years of their lives.", gifts:["Shepherding","Encouragement","Evangelism"], abilities:["Mentoring","Coaching","Connecting People"], people:["Youth"], causes:["Discipleship","Spiritual Apathy"], energy:"People-Oriented" },
  { name:"College / Young Adults", type:"inside", desc:"Invest in the next generation of leaders at one of the most pivotal seasons of life.", gifts:["Evangelism","Encouragement"], abilities:["Mentoring","Connecting People","Communicating"], people:["College Students","Young Married Couples"], causes:["Discipleship","Spiritual Apathy","Evangelism & Outreach"], energy:"People-Oriented" },
  { name:"Prayer & Next Step Room", type:"inside", desc:"Pray with and for people at their most vulnerable moments — right at the altar.", gifts:["Intercession","Faith","Discernment","Mercy"], abilities:["Counseling","Encouraging"], people:["Those in Recovery","Divorced / Single Parents"], causes:["Mental Health","Spiritual Apathy","Discipleship"], energy:null },
  { name:"Discipleship Groups", type:"inside", desc:"Lead others deeper into Scripture, community, and Christ-centered living.", gifts:["Teaching","Knowledge","Wisdom","Leadership"], abilities:["Teaching / Training","Mentoring","Facilitating","Leading"], people:[], causes:["Discipleship","Marriage & Family"], energy:null },
  { name:"Alpha", type:"outside", desc:"Facilitate open conversations about faith and life with people exploring or skeptical about Jesus.", gifts:["Evangelism","Faith","Hospitality"], abilities:["Communicating","Facilitating","Welcoming / Hospitality"], people:["College Students","Men","Women"], causes:["Spiritual Apathy","Evangelism & Outreach"], energy:"People-Oriented" },
  { name:"Circle of Friends (Special Needs)", type:"outside", desc:"Love and serve individuals with special needs and their families with patience and joy.", gifts:["Mercy","Helps","Encouragement"], abilities:["Encouraging","Welcoming / Hospitality"], people:["Disabled","Children","Elderly"], causes:["Mental Health","Education"], energy:"People-Oriented" },
  { name:"The Way (Women's Crisis Relief)", type:"outside", desc:"Come alongside women in crisis with compassion, practical help, and the hope of the gospel.", gifts:["Mercy","Shepherding","Intercession"], abilities:["Counseling","Encouraging"], people:["Women","Divorced / Single Parents","Those in Recovery"], causes:["Mental Health","Poverty & Hunger"], energy:"People-Oriented" },
  { name:"International Free Lunch Club (UTD)", type:"outside", desc:"Host international students with a meal and genuine community — often their first real connection in America.", gifts:["Hospitality","Evangelism","Encouragement"], abilities:["Welcoming / Hospitality","Connecting People"], people:["College Students","Internationals / Immigrants"], causes:["Evangelism & Outreach","Racial Reconciliation"], energy:"People-Oriented" },
  { name:"Bukhair Elementary Care Team", type:"outside", desc:"Serve as the hands and feet of Jesus in a local Title I school — tutoring, events, teacher support, and more.", gifts:["Helps","Mercy","Teaching","Encouragement"], abilities:["Teaching / Training","Organizing","Serving"], people:["Children"], causes:["Education","At-risk Children","Poverty & Hunger"], energy:null },
  { name:"Car Care", type:"outside", desc:"Use your mechanical skills to practically serve single parents, widows, and those who can't afford repairs.", gifts:["Helps","Mercy"], abilities:["Building / Craftsmanship","Serving"], people:["Divorced / Single Parents","Elderly","Women"], causes:["Poverty & Hunger"], energy:"Task-Oriented" },
  { name:"ESL Ministry", type:"outside", desc:"Teach English to non-native speakers — no bilingual skills required. Just patience and a welcoming spirit.", gifts:["Teaching","Hospitality","Encouragement"], abilities:["Teaching / Training","Welcoming / Hospitality","Communicating"], people:["Internationals / Immigrants"], causes:["Education","Racial Reconciliation","Evangelism & Outreach"], energy:"People-Oriented" },
  { name:"Kids Point (After-School Program)", type:"outside", desc:"Bring the gospel to low-income apartment kids through games, Bible stories, and consistent presence.", gifts:["Evangelism","Teaching","Mercy","Encouragement"], abilities:["Teaching / Training","Coaching","Performing (music, drama, etc.)"], people:["Children"], causes:["At-risk Children","Poverty & Hunger","Evangelism & Outreach","Education"], energy:"People-Oriented" },
  { name:"Quilted Blessings / Prayer Shawl", type:"outside", desc:"Use your hands to create tangible expressions of love and prayer for people in need.", gifts:["Helps","Intercession"], abilities:["Building / Craftsmanship"], people:["Elderly","Disabled"], causes:["Care for the Elderly","Mental Health"], energy:"Task-Oriented" }
];

var summaryMap = {
  "Administration": "You're a systems thinker who makes ministry run well. You'll thrive in roles that need structure, coordination, and behind-the-scenes excellence.",
  "Evangelism": "You're wired to reach people who don't yet know Jesus. You'll thrive anywhere the gospel is being shared with the unchurched.",
  "Faith": "You carry a contagious trust in God that inspires those around you. You'll thrive in prayer-focused and mission-driven environments.",
  "Mercy": "You're drawn to people in pain and you meet them there without flinching. You'll thrive in care-focused and compassion ministry.",
  "Leadership": "You can see where things need to go and rally people to get there. You'll thrive in roles with vision, responsibility, and a team to develop.",
  "Teaching": "You love helping people understand truth and apply it to their lives. You'll thrive in discipleship, small groups, and education-focused ministry.",
  "Giving": "You steward resources as a form of worship. You'll thrive supporting ministry and generosity initiatives behind the scenes.",
  "Intercession": "You carry a deep burden to pray — and things move when you do. You'll thrive in prayer ministry and care-focused serving.",
  "Discernment": "You have a sharp spiritual sensitivity that protects and guides others. You'll thrive in prayer, pastoral care, and leadership support roles.",
  "Encouragement": "You have a gift for calling out the best in people. You'll thrive anywhere people need someone in their corner — which is everywhere."
};

// ── STATE ─────────────────────────────────────────────────────────
var currentStep = 0;

// ── HELPERS ───────────────────────────────────────────────────────
function goTo(n) {
  document.querySelectorAll('.card').forEach(function(c){ c.classList.remove('active'); });
  document.getElementById('step-' + n).classList.add('active');
  currentStep = n;
  var pct = n === 0 ? 0 : Math.round(n / 5 * 100);
  document.getElementById('progressBar').style.width = pct + '%';
  var dots = document.getElementById('stepDots');
  dots.innerHTML = '';
  for (var i = 1; i <= 5; i++) {
    var d = document.createElement('div');
    d.className = 'step-dot' + (i === n ? ' active' : i < n ? ' done' : '');
    dots.appendChild(d);
  }
  window.scrollTo({ top: 0, behavior: 'smooth' });
}

function makeCheckboxes(containerId, options) {
  var c = document.getElementById(containerId);
  options.forEach(function(opt) {
    var l = document.createElement('label');
    l.className = 'cb-item';
    l.innerHTML = '<input type="checkbox" value="' + opt + '"><div class="cb-box"></div><span>' + opt + '</span>';
    c.appendChild(l);
  });
}

function makePersonality(containerId, pairs, prefix) {
  var c = document.getElementById(containerId);
  pairs.forEach(function(pair, i) {
    var wrap = document.createElement('div');
    wrap.className = 'p-row-wrap';
    var lbl = document.createElement('div');
    lbl.className = 'p-row-label';
    lbl.textContent = 'Choose one ↓';
    var d = document.createElement('div');
    d.className = 'p-row';
    d.id = prefix + '_row_' + i;
    d.innerHTML =
      '<label class="p-btn-label"><input type="radio" name="' + prefix + '_' + i + '" value="1"><div class="p-btn">' + pair[0] + '</div></label>' +
      '<label class="p-btn-label"><input type="radio" name="' + prefix + '_' + i + '" value="4"><div class="p-btn">' + pair[1] + '</div></label>';
    // Remove unanswered highlight once selected
    d.addEventListener('change', function() {
      d.classList.remove('unanswered');
    });
    wrap.appendChild(lbl);
    wrap.appendChild(d);
    c.appendChild(wrap);
  });
}

// ── INIT ──────────────────────────────────────────────────────────
function init() {
  // Gift questions
  var gc = document.getElementById('giftQs');
  giftQs.forEach(function(q, i) {
    var d = document.createElement('div');
    d.className = 'gq';
    var sc = '';
    var labels = ['0','1','2','3'];
    for (var v = 0; v <= 3; v++) {
      sc += '<label><input type="radio" name="g_' + i + '" value="' + v + '"><div class="dot">' + v + '</div></label>';
    }
    d.innerHTML = '<span class="qn">' + (i+1) + '</span><span class="qt">' + q.text + '</span><div class="qs">' + sc + '</div>';
    gc.appendChild(d);
  });

  makeCheckboxes('heartPeople', heartPeopleOpts);
  makeCheckboxes('heartCauses', heartCausesOpts);
  makeCheckboxes('abilitiesList', abilitiesOpts);
  makePersonality('energyRows', energyPairs, 'energy');
  makePersonality('organizeRows', orgPairs, 'org');

  // Button listeners
  document.getElementById('beginBtn').addEventListener('click', startAssessment);
  document.getElementById('back1').addEventListener('click', function(){ goTo(0); });
  document.getElementById('next1').addEventListener('click', validateGifts);
  document.getElementById('back2').addEventListener('click', function(){ goTo(1); });
  document.getElementById('next2').addEventListener('click', function(){ goTo(3); });
  document.getElementById('back3').addEventListener('click', function(){ goTo(2); });
  document.getElementById('next3').addEventListener('click', function(){ goTo(4); });
  document.getElementById('back4').addEventListener('click', function(){ goTo(3); });
  document.getElementById('next4').addEventListener('click', validatePersonality);
  document.getElementById('back5').addEventListener('click', function(){ goTo(4); });
  document.getElementById('submitBtn').addEventListener('click', submitAssessment);

  // Password gate
  var STAFF_PASSWORD = 'heights2024'; // ← change this to your preferred password
  var staffUnlocked = false;

  document.getElementById('editToggle').addEventListener('click', function(){
    if (staffUnlocked) {
      openEditPanel();
    } else {
      var gate = document.getElementById('pwGate');
      gate.style.display = 'flex';
      document.getElementById('pwInput').value = '';
      document.getElementById('pwError').textContent = '';
      setTimeout(function(){ document.getElementById('pwInput').focus(); }, 100);
    }
  });

  document.getElementById('pwSubmit').addEventListener('click', function(){
    var val = document.getElementById('pwInput').value;
    if (val === STAFF_PASSWORD) {
      document.getElementById('pwGate').style.display = 'none';
      staffUnlocked = true;
      openEditPanel();
    } else {
      document.getElementById('pwError').textContent = 'Incorrect password. Try again.';
      document.getElementById('pwInput').value = '';
      document.getElementById('pwInput').focus();
    }
  });

  document.getElementById('pwInput').addEventListener('keydown', function(e){
    if (e.key === 'Enter') document.getElementById('pwSubmit').click();
  });

  document.getElementById('pwCancel').addEventListener('click', function(){
    document.getElementById('pwGate').style.display = 'none';
  });

  document.getElementById('epClose').addEventListener('click', closeEditPanel);
  document.getElementById('epOverlay').addEventListener('click', closeEditPanel);
  document.getElementById('epApply').addEventListener('click', applyEdits);

  function openEditPanel() {
    document.getElementById('editPanel').classList.add('open');
    document.getElementById('epOverlay').classList.add('open');
  }
  function closeEditPanel() {
    document.getElementById('editPanel').classList.remove('open');
    document.getElementById('epOverlay').classList.remove('open');
  }

  goTo(0);
}

// ── VALIDATION ────────────────────────────────────────────────────
function startAssessment() {
  var f = document.getElementById('firstName').value.trim();
  var l = document.getElementById('lastName').value.trim();
  var e = document.getElementById('email').value.trim();
  var err = document.getElementById('err-0');
  if (!f || !l || !e || e.indexOf('@') === -1) {
    err.textContent = 'Please enter your first name, last name, and a valid email.';
    return;
  }
  err.textContent = '';
  goTo(1);
}

function validateGifts() {
  var missing = 0, first = -1;
  for (var i = 0; i < giftQs.length; i++) {
    if (!document.querySelector('input[name="g_' + i + '"]:checked')) {
      missing++;
      if (first < 0) first = i;
    }
  }
  if (missing > 0) {
    document.getElementById('err-1').textContent = 'Please answer all questions (' + missing + ' remaining).';
    document.querySelectorAll('.gq')[first].scrollIntoView({ behavior: 'smooth', block: 'center' });
    return;
  }
  document.getElementById('err-1').textContent = '';
  goTo(2);
}

function validatePersonality() {
  var missing = 0;
  for (var i = 0; i < energyPairs.length; i++) {
    var row = document.getElementById('energy_row_' + i);
    if (!document.querySelector('input[name="energy_' + i + '"]:checked')) {
      missing++;
      if (row) row.classList.add('unanswered');
    } else {
      if (row) row.classList.remove('unanswered');
    }
  }
  for (var i = 0; i < orgPairs.length; i++) {
    var row = document.getElementById('org_row_' + i);
    if (!document.querySelector('input[name="org_' + i + '"]:checked')) {
      missing++;
      if (row) row.classList.add('unanswered');
    } else {
      if (row) row.classList.remove('unanswered');
    }
  }
  if (missing > 0) {
    document.getElementById('err-4').textContent = 'Please select one option for each row (' + missing + ' remaining).';
    // Scroll to first unanswered
    var first = document.querySelector('.p-row.unanswered');
    if (first) first.scrollIntoView({ behavior: 'smooth', block: 'center' });
    return;
  }
  document.getElementById('err-4').textContent = '';
  goTo(5);
}

// ── SUBMIT & SCORE ────────────────────────────────────────────────
function submitAssessment() {
  // Score gifts
  var scores = {};
  giftQs.forEach(function(q, i) {
    var el = document.querySelector('input[name="g_' + i + '"]:checked');
    scores[q.gift] = (scores[q.gift] || 0) + (el ? parseInt(el.value) : 0);
  });
  var sorted = Object.keys(scores).map(function(k){ return { name: k, score: scores[k] }; });
  sorted.sort(function(a, b){ return b.score - a.score; });

  var people = Array.from(document.querySelectorAll('#heartPeople input:checked')).map(function(e){ return e.value; });
  var causes = Array.from(document.querySelectorAll('#heartCauses input:checked')).map(function(e){ return e.value; });
  var abilityList = Array.from(document.querySelectorAll('#abilitiesList input:checked')).map(function(e){ return e.value; });

  var eTotal = 0, oTotal = 0;
  for (var i = 0; i < energyPairs.length; i++) {
    var el = document.querySelector('input[name="energy_' + i + '"]:checked');
    eTotal += el ? parseInt(el.value) : 0;
  }
  for (var i = 0; i < orgPairs.length; i++) {
    var el = document.querySelector('input[name="org_' + i + '"]:checked');
    oTotal += el ? parseInt(el.value) : 0;
  }

  var eType = eTotal <= energyPairs.length * 2.5 ? 'Task-Oriented' : 'People-Oriented';
  var eDesc = eType === 'Task-Oriented' ? 'You are energized by accomplishing goals and moving projects forward.' : 'You are energized by relationships, community, and connecting with people.';
  var oType = oTotal <= orgPairs.length * 2.5 ? 'Flexible / Spontaneous' : 'Structured / Planned';
  var oDesc = oType === 'Flexible / Spontaneous' ? 'You thrive with freedom and variety — you adapt well on the fly.' : 'You thrive with clear plans and routines — structure helps you do your best work.';

  var first = document.getElementById('firstName').value.trim();
  var last  = document.getElementById('lastName').value.trim();

  // Results header
  document.getElementById('rName').textContent = first + ' ' + last;
  var tags = document.getElementById('shapeTags');
  tags.innerHTML = '';
  sorted.slice(0, 3).forEach(function(g) {
    var s = document.createElement('span'); s.className = 's-tag'; s.textContent = g.name; tags.appendChild(s);
  });
  [eType, oType].forEach(function(t) {
    var s = document.createElement('span'); s.className = 's-tag'; s.textContent = t; tags.appendChild(s);
  });

  // Gift bars
  var barsEl = document.getElementById('giftBars');
  barsEl.innerHTML = '';
  sorted.forEach(function(g, i) {
    var pct = Math.round((g.score / 3) * 100);
    var row = document.createElement('div');
    row.className = 'bar-row';
    row.innerHTML = '<span class="bar-name">' + g.name + (i < 3 ? '<span class="top-badge">Top</span>' : '') + '</span><div class="bar-wrap"><div class="bar-fill' + (i < 3 ? ' top' : '') + '" style="width:0%" data-pct="' + pct + '"></div></div><span class="bar-score">' + g.score + '/3</span>';
    barsEl.appendChild(row);
  });

  // Heart & Abilities
  var none = '<span style="color:var(--gray);font-size:.83rem">None selected</span>';
  document.getElementById('rPeople').innerHTML    = people.length    ? people.map(function(p){ return '<span class="tag">' + p + '</span>'; }).join('') : none;
  document.getElementById('rCauses').innerHTML    = causes.length    ? causes.map(function(c){ return '<span class="tag">' + c + '</span>'; }).join('') : none;
  document.getElementById('rAbilities').innerHTML = abilityList.length ? abilityList.map(function(a){ return '<span class="tag">' + a + '</span>'; }).join('') : none;

  // Personality
  document.getElementById('rEnergyVal').textContent = eType;
  document.getElementById('rEnergyDesc').textContent = eDesc;
  document.getElementById('rOrgVal').textContent = oType;
  document.getElementById('rOrgDesc').textContent = oDesc;

  // Experience
  var expEl = document.getElementById('rExp');
  expEl.innerHTML = '';
  [['Spiritual Experiences','expSpiritual'],['Painful Experiences','expPainful'],['Education & Work','expEducation'],['Ministry Experience','expMinistry']].forEach(function(pair) {
    var val = document.getElementById(pair[1]).value.trim();
    if (val) expEl.innerHTML += '<div class="exp-r"><div class="exp-r-label">' + pair[0] + '</div><div class="exp-r-text">' + val + '</div></div>';
  });

  // Team matching
  var teamScores = servingTeams.map(function(team) {
    var score = 0;
    sorted.slice(0, 3).forEach(function(g, rank) {
      if (team.gifts.indexOf(g.name) !== -1) score += rank === 0 ? 5 : rank === 1 ? 3 : 2;
    });
    abilityList.forEach(function(a) { if (team.abilities.indexOf(a) !== -1) score += 2; });
    people.forEach(function(p) { if (team.people.indexOf(p) !== -1) score += 2; });
    causes.forEach(function(c) { if (team.causes.indexOf(c) !== -1) score += 2; });
    if (team.energy && team.energy === eType) score += 1;
    return Object.assign({}, team, { score: score });
  });
  teamScores.sort(function(a, b){ return b.score - a.score; });

  var topInside  = teamScores.filter(function(t){ return t.type === 'inside'; }).slice(0, 3);
  var topOutside = teamScores.filter(function(t){ return t.type === 'outside'; }).slice(0, 3);
  var medals = ['🥇','🥈','🥉'];
  var topGiftName = sorted[0] ? sorted[0].name : '';
  var profileText = summaryMap[topGiftName] || 'God has shaped you in a unique way. Here are the serving areas that fit you best.';

  var matchHTML = '<div class="match-profile"><strong>Your Serving Profile</strong>' + profileText + '</div>';
  matchHTML += '<div class="match-type-label">Inside The Heights</div>';
  topInside.forEach(function(t, i) {
    matchHTML += '<div class="match-card"><div class="match-card-name">' + medals[i] + ' ' + t.name + '</div><div class="match-card-desc">' + t.desc + '</div></div>';
  });
  matchHTML += '<div class="match-type-label">Beyond Our Walls</div>';
  topOutside.forEach(function(t, i) {
    matchHTML += '<div class="match-card"><div class="match-card-name">' + medals[i] + ' ' + t.name + '</div><div class="match-card-desc">' + t.desc + '</div></div>';
  });
  document.getElementById('rMatches').innerHTML = matchHTML;

  // Populate PDF header
  document.getElementById('pdfName').textContent = first + ' ' + last;
  var now = new Date();
  var dateStr = now.toLocaleDateString('en-US', { month: 'long', day: 'numeric', year: 'numeric' });
  var dateEl = document.getElementById('pdfDate');
  if (dateEl) dateEl.textContent = dateStr;
  var pdfTagsEl = document.getElementById('pdfTags');
  if (pdfTagsEl) {
    pdfTagsEl.innerHTML = '';
    sorted.slice(0,3).forEach(function(g){
      var s = document.createElement('span'); s.className='pdf-s-tag'; s.textContent=g.name; pdfTagsEl.appendChild(s);
    });
    [eType, oType].forEach(function(t){
      var s = document.createElement('span'); s.className='pdf-s-tag'; s.textContent=t; pdfTagsEl.appendChild(s);
    });
  }

  // Show results
  document.querySelectorAll('.card').forEach(function(c){ c.classList.remove('active'); });
  document.getElementById('stepDots').style.display = 'none';
  document.getElementById('results').style.display = 'block';
  window.scrollTo({ top: 0, behavior: 'smooth' });
  setTimeout(function() {
    document.querySelectorAll('.bar-fill').forEach(function(b){ b.style.width = b.dataset.pct + '%'; });
  }, 250);

  // Send to Formspree
  var insideNames  = topInside.map(function(t){ return t.name; }).join(', ');
  var outsideNames = topOutside.map(function(t){ return t.name; }).join(', ');
  sendToStaff({
    _subject: 'SHAPE Assessment: ' + first + ' ' + last,
    name: first + ' ' + last,
    email: document.getElementById('email').value.trim(),
    phone: document.getElementById('phone').value.trim() || 'Not provided',
    top_gifts: sorted.slice(0, 3).map(function(g){ return g.name + ' (' + g.score + '/3)'; }).join(', '),
    all_gift_scores: sorted.map(function(g){ return g.name + ': ' + g.score; }).join(' | '),
    heart_people: people.join(', ') || 'None',
    heart_causes: causes.join(', ') || 'None',
    abilities: abilityList.join(', ') || 'None',
    personality: eType + ' / ' + oType,
    suggested_inside_teams: insideNames,
    suggested_outside_teams: outsideNames,
    spiritual_experiences: document.getElementById('expSpiritual').value.trim() || '—',
    painful_experiences:   document.getElementById('expPainful').value.trim() || '—',
    education_background:  document.getElementById('expEducation').value.trim() || '—',
    ministry_experience:   document.getElementById('expMinistry').value.trim() || '—'
  });
}

function sendToStaff(data) {
  // Silent Google Forms submission — invisible to the user
  var FORM_ACTION = 'https://docs.google.com/forms/d/e/1FAIpQLSevB8IwUxXRnK1er71LARHFlklOLT_qgFhLr8bfnm7rl5qYQA/formResponse';
  var params = new URLSearchParams({
    'entry.1432104164': data.name                    || '',
    'entry.1987404178': data.email                   || '',
    'entry.94070104':   data.phone                   || '',
    'entry.843741673':  data.top_gifts               || '',
    'entry.647789225':  data.all_gift_scores         || '',
    'entry.1965310796': data.heart_people            || '',
    'entry.220905419':  data.heart_causes            || '',
    'entry.1682210242': data.abilities               || '',
    'entry.265600163':  data.personality             || '',
    'entry.1184419729': data.suggested_inside_teams  || '',
    'entry.121349921':  data.suggested_outside_teams || '',
    'entry.1048405513': data.spiritual_experiences   || '',
    'entry.470138756':  data.painful_experiences     || '',
    'entry.414091651':  data.education_background    || '',
    'entry.1265499534': data.ministry_experience     || ''
  });
  // Use no-cors mode — Google Forms doesn't allow CORS but the data still posts
  fetch(FORM_ACTION, {
    method: 'POST',
    mode: 'no-cors',
    headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
    body: params.toString()
  }).catch(function(e){ console.warn('Form submission error:', e); });
}

// ── EDIT PANEL ────────────────────────────────────────────────────
function applyEdits() {
  var t1  = document.getElementById('ep_t1').value;
  var t2  = document.getElementById('ep_t2').value;
  var sub = document.getElementById('ep_sub').value;
  var mt = document.querySelector('.main-title');
  if (mt) mt.innerHTML = t1 + '<br><span>' + t2 + '</span>';
  var st = document.querySelector('.sub-text');
  if (st) st.textContent = sub;
  var ctaH = document.querySelector('.cta h3');
  var ctaB = document.querySelector('.cta p');
  var ctaBtn = document.querySelector('.btn-gold');
  var footerEmail = document.querySelector('#results div:last-child strong');
  if (ctaH) ctaH.textContent = document.getElementById('ep_ctaH').value;
  if (ctaB) ctaB.textContent = document.getElementById('ep_ctaB').value;
  if (ctaBtn) ctaBtn.textContent = document.getElementById('ep_ctaBtn').value;
  if (footerEmail) footerEmail.textContent = document.getElementById('ep_email').value;
  document.getElementById('editPanel').classList.remove('open');
  document.getElementById('epOverlay').classList.remove('open');
  var btn = document.getElement
  btn.textContent = 'Admin';
  setTimeout(function(){ btn.textContent = 'Admin'; }, 2000);
}

// ── START ─────────────────────────────────────────────────────────
init();
</script>
</body>
</html>
