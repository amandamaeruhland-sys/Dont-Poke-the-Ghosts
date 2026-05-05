[dont-poke-the-ghosts-website.html](https://github.com/user-attachments/files/27415704/dont-poke-the-ghosts-website.html)
# Dont-Poke-the-Ghosts
Podcast website
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Don't Poke the Ghosts — A 50-State Supernatural Podcast</title>
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=IM+Fell+English:ital@0;1&family=Cinzel:wght@400;600;900&family=Lora:ital,wght@0,400;0,600;1,400&display=swap" rel="stylesheet" />
<script src="https://unpkg.com/react@18/umd/react.production.min.js" crossorigin></script>
<script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js" crossorigin></script>
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
<style>
*{box-sizing:border-box;margin:0;padding:0;cursor:url('moth-cursor.svg') 40 24, auto}
:root{
  --bg:#123524;--bg2:#0e2b1d;--bgc:#163d29;--bgh:#1a4430;
  --t:#e8dfc8;--tm:#8aaa91;--td:#4a6b55;
  --gold:#c9a84c;--goldd:rgba(201,168,76,0.15);
  --rust:#9b3a2a;--moss:#6aaa70;
  --b:#1e4530;--bm:#285c3e;
}
html,body{background:var(--bg);color:var(--t);font-family:'Lora',Georgia,serif;font-size:16px;line-height:1.75;min-height:100vh}
#root{min-height:100vh;display:flex;flex-direction:column}
h1,h2,h3,h4{font-family:'Cinzel','Times New Roman',serif;font-weight:600;letter-spacing:.05em;line-height:1.15;color:var(--t)}
a{color:var(--gold);text-decoration:none}
a:hover{text-decoration:underline}
.ctr{max-width:1100px;margin:0 auto;padding:0 1.5rem}
.ctrn{max-width:760px;margin:0 auto;padding:0 1.5rem}

/* Nav */
nav{background:var(--bg);border-bottom:1px solid var(--b);position:sticky;top:0;z-index:100}
.ni{display:flex;align-items:center;justify-content:space-between;padding:1rem 1.5rem;max-width:1100px;margin:0 auto;gap:1rem;flex-wrap:wrap}
.nb{font-family:'Cinzel',serif;font-weight:900;font-size:.9rem;letter-spacing:.12em;color:var(--t);text-transform:uppercase;cursor:pointer;background:none;border:none;white-space:nowrap;transition:color .2s}
.nb:hover{color:var(--gold)}
.nb span{color:var(--gold)}
.nl{display:flex;gap:1.75rem;list-style:none;flex-wrap:wrap}
.nl button{font-family:'Cinzel',serif;font-size:.68rem;letter-spacing:.14em;text-transform:uppercase;color:var(--tm);cursor:pointer;transition:color .2s;background:none;border:none}
.nl button:hover{color:var(--t)}
.nl button.act{color:var(--gold)}

/* Page header */
.ph{padding:4rem 1.5rem 3rem;border-bottom:1px solid var(--b);background:linear-gradient(180deg,var(--bg2) 0%,var(--bg) 100%)}
.ey{font-family:'Cinzel',serif;font-size:.65rem;letter-spacing:.3em;text-transform:uppercase;color:var(--gold);margin-bottom:1rem;display:block}
.pt{font-family:'Cinzel',serif;font-weight:900;font-size:clamp(2.2rem,6vw,4.5rem);line-height:1.05;letter-spacing:.04em}
.ps{font-family:'IM Fell English',Georgia,serif;font-style:italic;font-size:clamp(1rem,2vw,1.25rem);color:var(--tm);margin-top:.75rem;max-width:600px}

/* Divider */
.dv{display:flex;align-items:center;gap:1rem;margin:2.5rem 0}
.dv::before,.dv::after{content:'';flex:1;height:1px;background:var(--b)}
.dv span{color:var(--gold);opacity:.5;font-size:1rem;line-height:1}
.hr{border:none;border-top:1px solid var(--b);margin:2rem 0}

/* Cards */
.card{background:var(--bgc);border:1px solid var(--b);padding:1.5rem;transition:border-color .2s}
.card:hover{border-color:var(--bm)}

/* Tags */
.tag{display:inline-block;font-family:'Cinzel',serif;font-size:.6rem;letter-spacing:.15em;text-transform:uppercase;padding:.15rem .5rem;border:1px solid var(--rust);color:var(--rust)}
.tg{border-color:var(--gold);color:var(--gold)}
.tm2{border-color:var(--moss);color:var(--moss)}

/* Buttons */
.btn{display:inline-block;font-family:'Cinzel',serif;font-size:.7rem;letter-spacing:.12em;text-transform:uppercase;padding:.65rem 1.5rem;border:1px solid var(--gold);color:var(--gold);background:transparent;cursor:pointer;transition:background .2s,color .2s;text-decoration:none}
.btn:hover{background:var(--gold);color:var(--bg);text-decoration:none}
.btng{border-color:var(--bm);color:var(--tm)}
.btng:hover{background:var(--bm);color:var(--t)}

/* Section label */
.sl{font-family:'Cinzel',serif;font-size:.62rem;letter-spacing:.25em;text-transform:uppercase;color:var(--gold);margin-bottom:.4rem}
.ep{font-family:'Cinzel',serif;font-size:.6rem;letter-spacing:.2em;color:var(--td)}

/* Grids */
.g2{display:grid;grid-template-columns:repeat(auto-fill,minmax(320px,1fr));gap:1px;background:var(--b)}
.g2>*{background:var(--bg)}
.g3{display:grid;grid-template-columns:repeat(auto-fill,minmax(260px,1fr));gap:1.5rem}

/* Input */
.inp{background:var(--bgc);border:1px solid var(--b);color:var(--t);font-family:'Lora',serif;font-size:.9rem;padding:.6rem 1rem;width:100%;outline:none;transition:border-color .2s}
.inp::placeholder{color:var(--td);font-style:italic}
.inp:focus{border-color:var(--gold)}

/* Play btn */
.pb{width:2.5rem;height:2.5rem;border:1px solid var(--gold);background:transparent;color:var(--gold);cursor:pointer;display:flex;align-items:center;justify-content:center;flex-shrink:0;font-size:.9rem;transition:all .2s}
.pb:hover{background:var(--gold);color:var(--bg)}

/* Progress */
.prg{flex:1;height:2px;background:var(--bm);cursor:pointer;position:relative}
.prf{height:100%;background:var(--gold)}

/* Footer */
footer{margin-top:auto;border-top:1px solid var(--b);padding:2.5rem 1.5rem;background:var(--bg2)}
.fi{max-width:1100px;margin:0 auto;display:flex;justify-content:space-between;align-items:flex-start;flex-wrap:wrap;gap:2rem}
.fb{font-family:'Cinzel',serif;font-size:.8rem;letter-spacing:.1em;color:var(--tm)}
.fb strong{display:block;font-size:1rem;color:var(--t);margin-bottom:.3rem}
.fl{display:flex;gap:1.5rem;list-style:none;flex-wrap:wrap}
.fl button{font-family:'Cinzel',serif;font-size:.65rem;letter-spacing:.12em;text-transform:uppercase;color:var(--td);background:none;border:none;cursor:pointer;transition:color .2s}
.fl button:hover{color:var(--gold)}

/* Home hero */
.hh{min-height:85vh;display:flex;flex-direction:column;align-items:center;justify-content:center;text-align:center;padding:4rem 1.5rem;position:relative;overflow:hidden;background:radial-gradient(ellipse at 50% 0%,rgba(201,168,76,.05) 0%,transparent 60%),var(--bg)}
.hh::before{content:'';position:absolute;inset:0;background:repeating-linear-gradient(0deg,transparent,transparent 39px,rgba(255,255,255,.015) 39px,rgba(255,255,255,.015) 40px);pointer-events:none}
.hte{font-family:'Cinzel',serif;font-size:.65rem;letter-spacing:.4em;text-transform:uppercase;color:var(--gold);margin-bottom:1.5rem}
.ht{font-family:'Cinzel',serif;font-weight:900;font-size:clamp(3rem,10vw,7rem);line-height:.95;color:var(--t);letter-spacing:.04em;position:relative;z-index:1}
.ht .gw{color:var(--gold)}
.hd{font-family:'IM Fell English',Georgia,serif;font-style:italic;font-size:clamp(1.1rem,2.5vw,1.4rem);color:var(--tm);margin-top:1.5rem;max-width:580px;line-height:1.6}
.hc{display:flex;gap:1rem;margin-top:2.5rem;flex-wrap:wrap;justify-content:center}

/* Scrollbar */
::-webkit-scrollbar{width:5px}
::-webkit-scrollbar-track{background:var(--bg)}
::-webkit-scrollbar-thumb{background:var(--bm)}
::-webkit-scrollbar-thumb:hover{background:var(--gold)}

/* Transcript viewer */
.tv{display:grid;grid-template-columns:260px 1fr;border:1px solid var(--b);min-height:600px}
.ts{border-right:1px solid var(--b);overflow-y:auto;max-height:700px}
.tsi{width:100%;text-align:left;padding:.9rem 1rem;border-bottom:1px solid var(--b);cursor:pointer;transition:background .15s;font:inherit;color:inherit;background:var(--bg);border-left:2px solid transparent}
.tsi:hover{background:var(--bg2)}
.tsi.act{background:var(--bgh);border-left-color:var(--gold)}
.tc{padding:2rem;overflow-y:auto;max-height:700px}

/* Video thumb */
.vt{background:var(--bgc);border:1px solid var(--b);overflow:hidden;cursor:pointer;transition:border-color .2s}
.vt:hover{border-color:var(--bm)}
.vti{width:100%;aspect-ratio:16/9;background:var(--bg2);display:flex;align-items:center;justify-content:center;position:relative;overflow:hidden}
.vpo{position:absolute;inset:0;display:flex;align-items:center;justify-content:center;background:rgba(13,12,10,.4);transition:background .2s}
.vt:hover .vpo{background:rgba(13,12,10,.2)}
.vpl{width:3rem;height:3rem;border:2px solid var(--gold);display:flex;align-items:center;justify-content:center;color:var(--gold);font-size:1rem}

/* Gallery */
.gg{display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:2px;background:var(--b)}
.gi{background:var(--bgc);cursor:pointer;position:relative;overflow:hidden}
.gio{position:absolute;inset:0;background:rgba(13,12,10,0);transition:background .25s;display:flex;align-items:flex-end}
.gi:hover .gio{background:rgba(13,12,10,.65)}
.gip{padding:1rem;width:100%;opacity:0;transition:opacity .25s}
.gi:hover .gip{opacity:1}

/* Source item */
.si{display:flex;gap:1rem;padding:.75rem 0;border-bottom:1px solid var(--b);align-items:flex-start}

@media(max-width:700px){
  .tv{grid-template-columns:1fr}
  .ts{max-height:200px;border-right:none;border-bottom:1px solid var(--b)}
  .nl{gap:1rem}
}
@media(max-width:480px){.ni{flex-direction:column;align-items:flex-start}}
@media(max-width:640px){.ab2c{grid-template-columns:1fr!important}}
</style>
</head>
<body>
<div id="root"></div>

<script type="text/babel" data-presets="react">

const { useState, useCallback } = React;

/* ============================================================
   DATA
============================================================ */
const STATES = ['AL','AK','AZ','AR','CA','CO','CT','DE','FL','GA','HI','ID','IL','IN','IA','KS','KY','LA','ME','MD','MA','MI','MN','MS','MO','MT','NE','NV','NH','NJ','NM','NY','NC','ND','OH','OK','OR','PA','RI','SC','SD','TN','TX','UT','VT','VA','WA','WV','WI','WY'];

const EPISODES = [
  {ep:1,state:'Alabama',abbr:'AL',date:'Jan 2024',duration:'1:21:13',
   segments:[
    {type:'Cryptid',title:'The White Thang',guest:'Billy Ray from Tuscaloosa',
     premise:"Billy Ray's hunting dogs refused to enter the woods. Something massive, white, and smelling like death has been circling his property.",
     lines:[
      {spk:'Host',t:"Billy Ray, thank you for calling in. Tell me about the dogs first."},
      {spk:'Billy Ray',t:"They just stopped. Sat down. Wouldn't move. These are good dogs — they go after hogs. They don't stop for nothing."},
      {spk:'Host',t:"That is the most important thing you've said. Animals know first. Always. Their instincts predate ours by millennia. The White Thang has haunted northern Alabama since at least the 1940s. Morgan County, Lawrence County, Moulton. No face. Just white fur and a particular kind of dread."},
      {spk:'Billy Ray',t:"No face?"},
      {spk:'Host',t:"No face. White entities in folklore almost universally represent boundary-crossers — things that exist between states of being. It doesn't need a face where it comes from. Now. Salt. You have salt in that house?"},
      {spk:'Billy Ray',t:"Course I do."},
      {spk:'Host',t:"Every threshold. Tonight. Salt is not folk superstition, Billy Ray. It is protective magic with a very long resume."},
     ]},
    {type:'Urban Legend',title:"Hell's Gate Bridge & Dead Children's Playground",guest:'Suzanne, history teacher, Oxford AL',
     premise:"Three students turned in papers on three legends Suzanne didn't know were connected. She's been up three nights since.",
     lines:[
      {spk:'Host',t:"Three students. Three connected legends. Independently. Suzanne — that's not coincidence. That's the land telling you something."},
      {spk:'Suzanne',t:"I'm a history teacher. I don't usually think about it that way."},
      {spk:'Host',t:"History and haunting are not separate disciplines. Dead Children's Playground in Maple Hill Cemetery — a genuine playground, in a genuine cemetery, with genuinely documented apparition reports. The combination of the mundane and the sacred is exactly where things get permeable."},
      {spk:'Suzanne',t:"Two of the kids said they felt watched when they went to research it."},
      {spk:'Host',t:"Good. That means they were paying attention. The Boyington Oak — a man who predicted his own posthumous vindication through a specific botanical event, and was right. The tree grew. That's not nothing."},
     ]},
   ]},
  {ep:2,state:'Alaska',abbr:'AK',date:'Feb 2024',duration:'1:24:46',
   segments:[
    {type:'Cryptid',title:'The Iliamna Lake Monster',guest:'Pete, bush pilot, King Salmon AK',
     premise:"Pete has flown over Lake Iliamna hundreds of times. He knows what a beluga looks like from the air. This was not a beluga.",
     lines:[
      {spk:'Host',t:"Pete, you're calling me from a layover. I appreciate your priorities."},
      {spk:'Pete',t:"My passengers saw it first. Something — maybe thirty feet? Just below the surface, moving parallel to us."},
      {spk:'Host',t:"Lake Iliamna is roughly the size of Connecticut. Science has barely bothered to study it. Water is the oldest mirror — what lives beneath it reflects something true about a place. Your aerial distance is exactly correct. Document. Observe. Do not attempt contact."},
      {spk:'Pete',t:"Wasn't planning on it."},
      {spk:'Host',t:"I find it telling that 'a known shark' is somehow more comforting than 'unknown entity.' Pacific Sleeper Sharks enter freshwater. They are both large and toothy. The distinction feels academic from thirty feet up."},
     ]},
    {type:'Urban Legend',title:'The Alaska Triangle',guest:'Ron, search and rescue coordinator, Juneau',
     premise:"Ron told a reporter 'there's nothing to it.' He has since looked at his own missing persons files.",
     lines:[
      {spk:'Host',t:"Ron. You said, on camera, 'there's nothing to it.' And then you looked at your files."},
      {spk:'Ron',t:"Since 1988, over sixteen thousand people have gone missing in Alaska. That's four times the national average."},
      {spk:'Host',t:"The Hale Boggs disappearance alone — a congressional delegation, one of the largest searches ever mounted, zero trace. I do not consider that a weather story. Ron, your missing persons files are the most authoritative source on this subject in the state. I suggest reading them with fresh eyes and noting any geographic clustering."},
      {spk:'Ron',t:"There is clustering. I didn't want to say that on camera."},
      {spk:'Host',t:"The 'watched from everywhere at once' experience reported by search and rescue personnel is consistent with descriptions of liminal wilderness zones across multiple traditions. The host takes that sensory report seriously."},
     ]},
   ]},
  {ep:3,state:'Arizona',abbr:'AZ',date:'Mar 2024',duration:'1:23:39',
   segments:[
    {type:'Cryptid',title:'The Mogollon Monster',guest:'Cactus Pete, retired park ranger, Payson AZ',
     premise:"Pete worked the Mogollon Rim for 30 years and never believed. Then he found the footprints.",
     lines:[
      {spk:'Host',t:"It's MOE-gee-on, Pete. Not muh-GO-yun. I will say this as many times as necessary."},
      {spk:'Cactus Pete',t:"Been calling it that my whole career."},
      {spk:'Host',t:"Thirty years of disrespectful pronunciation is how you get footprints on your morning walk. The Mogollon Monster has been reported since the early 1900s along that 200-mile escarpment. Over seven feet. Dark hair. Overwhelming stench. The White Mountain Apache have their own traditions about giant hairy beings in these mountains. This is not a new story."},
      {spk:'Cactus Pete',t:"The prints were huge. I've seen bear prints. This wasn't—"},
      {spk:'Host',t:"A creature that reportedly eats porcupines whole is communicating something very specific about its relationship with pain and consequence. I respect that tremendously. I suggest you also respect it from a significant distance."},
     ]},
    {type:'Urban Legend',title:'El Tiradito & The Wishing Shrine',guest:"Consuela, folklorist, University of Arizona",
     premise:"Consuela is tired of seeing El Tiradito described as a 'quirky roadside attraction.' She has things to say.",
     lines:[
      {spk:'Host',t:"Consuela, set the record straight."},
      {spk:'Consuela',t:"El Tiradito — The Castaway — is a shrine in Barrio Viejo dedicated to a young man killed in a love triangle and buried in unconsecrated ground. The community started leaving candles. If your candle burns through the night, your wish is granted. It's on the National Register of Historic Places."},
      {spk:'Host',t:"El Tiradito is my kind of sacred site — informal, community-maintained, continuously active, built around a marginal figure. The sinner, not the saint. And the candle tradition is one of the most straightforward forms of petition magic in the American Southwest."},
      {spk:'Consuela',t:"Community gathering at the shrine directly prevented a highway from being built through the neighborhood."},
      {spk:'Host',t:"That is my favorite example of practical magic in American civic history. Full stop."},
     ]},
   ]},
  {ep:4,state:'Arkansas',abbr:'AR',date:'Apr 2024',duration:'1:19:52',
   segments:[
    {type:'Cryptid',title:'The Fouke Monster',guest:'Darla Jean, Miller County AR',
     premise:"Darla Jean calls from the last payphone in the county. She doesn't trust cell phones. Not for this.",
     lines:[
      {spk:'Host',t:"Darla Jean, you called from a payphone. The last one in Miller County, you said."},
      {spk:'Darla Jean',t:"I don't trust cell phones. Not for this kind of thing."},
      {spk:'Host',t:"I find that completely reasonable. The Fouke Monster entered national consciousness in 1971 when the Ford family reported a creature attacking their home. The 1972 film traumatized a generation of drive-in moviegoers. Seven feet. Reddish-brown hair. A loping three-toed stride. The Sulphur River Bottom is ancient wetland — swamp ecosystems are among the most supernaturally active environments on this continent."},
      {spk:'Darla Jean',t:"It hasn't come through the walls. Just the chicken coops."},
      {spk:'Host',t:"That it hasn't come through the walls suggests it's observing rather than hunting. An observing entity is preferable to a hungry one. Keep it that way. Three-toed tracks are a signature — measure them, photograph with scale, cast them in plaster."},
     ]},
    {type:'Cryptid',title:'The Ozark Howler',guest:'Cletus, cattle rancher, Newton County AR',
     premise:"Three head of cattle gone. No tracks. No blood trail. No explanation.",
     lines:[
      {spk:'Host',t:"Cletus. Newton County. You've ranched the Ozarks your whole life."},
      {spk:'Cletus',t:"I know mountain lion kills. I know coyote kills. I do not know this."},
      {spk:'Host',t:"The Ozark Howler — also called the Black Howler, the Devil Cat — is described as a large black felid with glowing red eyes and a howl like a wolf crossed with a bull elk. The absence of tracks is its most significant forensic signature. Something that kills without leaving a track is operating by different rules."},
      {spk:'Cletus',t:"What do I do tonight?"},
      {spk:'Host',t:"Perimeter salt lines around your remaining herd. Not because I'm certain what this is — but because protective tradition does not require certainty to be effective. Do it anyway."},
     ]},
   ]},
];

const SOURCES = [
  {state:'Alabama',ep:1,items:[
    {type:'Book',cit:"Coleman, Loren. Mysterious America. Paraview Pocket Books, 2007."},
    {type:'Book',cit:"Redfern, Nick. Monsters of the Lone Star State (and broader Southern cryptid surveys)."},
    {type:'Organization',cit:"Oxford Paranormal Society — local field investigation records."},
    {type:'Website',cit:"Atlas Obscura — Dead Children's Playground (Huntsville, AL) and Hell's Gate Bridge."},
    {type:'Historic Record',cit:"National Register of Historic Places — El Tiradito listing and community history."},
  ]},
  {state:'Alaska',ep:2,items:[
    {type:'Book',cit:"Bille, Matthew A. Rumors of Existence. Hancock House, 1995."},
    {type:'Archive',cit:"Anchorage Daily News historical archive — 1940s–1950s Lake Iliamna sighting reports."},
    {type:'Organization',cit:"Alaska Search and Rescue — missing persons records, geographic cluster analysis."},
  ]},
  {state:'Arizona',ep:3,items:[
    {type:'Book',cit:"Mitchell, John. The Mogollon Monster: Arizona's Bigfoot. Renaissance Publishing, 2010."},
    {type:'Database',cit:"Bigfoot Field Researchers Organization (BFRO) — Mogollon Rim sighting database."},
    {type:'Historic Record',cit:"National Register of Historic Places — El Tiradito, Barrio Viejo, Tucson AZ."},
    {type:'Cultural Record',cit:"White Mountain Apache Nation — oral traditions regarding large bipedal beings in the Rim region."},
  ]},
  {state:'Arkansas',ep:4,items:[
    {type:'Book',cit:"Smoote, Miller, and Smith, Earl E. The Fouke Monster. 1974."},
    {type:'Film',cit:"The Legend of Boggy Creek. Dir. Charles B. Pierce, 1972. Primary cultural artifact."},
    {type:'Database',cit:"Arkansas Game & Fish Commission — large predator incident records, Newton County."},
    {type:'Book',cit:"Mogg, Rob. Classified Cryptids."},
  ]},
  {state:'General Resources',ep:0,items:[
    {type:'Book',cit:"Coleman, Loren & Clark, Jerome. Cryptozoology A to Z. Fireside, 1999."},
    {type:'Book',cit:"Guiley, Rosemary Ellen. The Encyclopedia of Ghosts and Spirits. 3rd ed. Checkmark Books, 2007."},
    {type:'Website',cit:"Atlas Obscura — American sites of historical, folkloric, and supernatural significance."},
    {type:'Website',cit:"American Folklore Society (AmericanFolklore.net) — state-by-state folklore database."},
    {type:'Academic',cit:"Big Book of Montana Mysteries (BBMM) — cross-referenced for regional cryptid patterns."},
  ]},
];

const ART_ITEMS = [
  {id:1,title:'The White Thang',state:'Alabama',cryptid:'White Thang',medium:'Digital Illustration',ep:1},
  {id:2,title:"Hell's Gate at Midnight",state:'Alabama',cryptid:"Hell's Gate Bridge",medium:'Ink & Watercolor',ep:1},
  {id:3,title:'Below the Surface',state:'Alaska',cryptid:'Iliamna Lake Monster',medium:'Digital Illustration',ep:2},
  {id:4,title:'The Triangle',state:'Alaska',cryptid:'Alaska Triangle',medium:'Gouache',ep:2},
  {id:5,title:'On the Rim',state:'Arizona',cryptid:'Mogollon Monster',medium:'Woodcut Print',ep:3},
  {id:6,title:'El Tiradito by Candlelight',state:'Arizona',cryptid:'El Tiradito',medium:'Photography',ep:3},
  {id:7,title:'Three-Toed',state:'Arkansas',cryptid:'Fouke Monster',medium:'Linocut Print',ep:4},
  {id:8,title:'The Howl',state:'Arkansas',cryptid:'Ozark Howler',medium:'Charcoal',ep:4},
  {id:9,title:'Dark Watchers on the Ridge',state:'California',cryptid:'Dark Watchers',medium:'Digital Illustration',ep:5},
  {id:10,title:'San Luis Valley, 2 AM',state:'Colorado',cryptid:'San Luis UFOs',medium:'Oil Pastel',ep:6},
  {id:11,title:'Melon Heads of Shelton',state:'Connecticut',cryptid:'Melon Heads',medium:'Ink',ep:7},
  {id:12,title:'The Skunk Ape in the Glades',state:'Florida',cryptid:'Skunk Ape',medium:'Digital Illustration',ep:9},
];

const VIDEO_LIST = [
  {id:1,ep:1,state:'Alabama',title:'The White Thang',type:'Cryptid',dur:'42:18'},
  {id:2,ep:1,state:'Alabama',title:"Hell's Gate Bridge",type:'Urban Legend',dur:'38:55'},
  {id:3,ep:2,state:'Alaska',title:'Iliamna Lake Monster',type:'Cryptid',dur:'44:02'},
  {id:4,ep:2,state:'Alaska',title:'The Alaska Triangle',type:'Urban Legend',dur:'39:44'},
  {id:5,ep:3,state:'Arizona',title:'The Mogollon Monster',type:'Cryptid',dur:'47:11'},
  {id:6,ep:3,state:'Arizona',title:'El Tiradito',type:'Urban Legend',dur:'36:28'},
  {id:7,ep:4,state:'Arkansas',title:'The Fouke Monster',type:'Cryptid',dur:'41:33'},
  {id:8,ep:4,state:'Arkansas',title:'The Ozark Howler',type:'Cryptid',dur:'38:19'},
  {id:9,ep:5,state:'California',title:'The Dark Watchers',type:'Cryptid',dur:'43:57'},
  {id:10,ep:6,state:'Colorado',title:'San Luis Valley UFOs',type:'Urban Legend',dur:'45:22'},
  {id:11,ep:7,state:'Connecticut',title:'Melon Heads',type:'Cryptid',dur:'37:08'},
  {id:12,ep:9,state:'Florida',title:'The Skunk Ape',type:'Cryptid',dur:'44:39'},
];

const PLATFORMS = [
  {name:'Spotify',icon:'♫',col:'#1DB954'},
  {name:'Apple Podcasts',icon:'◎',col:'#fc3c44'},
  {name:'Google Podcasts',icon:'◉',col:'#4285f4'},
  {name:'Pocket Casts',icon:'◈',col:'#f43e37'},
  {name:'RSS Feed',icon:'⊞',col:'#c9a84c'},
];

/* ============================================================
   SVG ART PLACEHOLDER
============================================================ */
function ArtSVG({item}) {
  const s = item.id % 4;
  const bgs = ['#1a1208','#0d1a12','#1a0d0d','#0d0d1a','#121a0d','#1a120d'];
  const bg = bgs[item.id % bgs.length];
  const lines = Array.from({length:8},(_,i)=>i);
  const radials = Array.from({length:12},(_,i)=>{
    const a=(i/12)*Math.PI*2;
    return {x2:100+Math.cos(a)*80,y2:100+Math.sin(a)*80};
  });
  return (
    <svg viewBox="0 0 200 200" width="100%" height="100%" xmlns="http://www.w3.org/2000/svg">
      <rect width="200" height="200" fill={bg}/>
      {lines.map(i=><line key={i} x1="0" y1={10+i*25} x2="200" y2={10+i*25} stroke="rgba(255,255,255,0.015)" strokeWidth="1"/>)}
      {s===0&&<>
        <circle cx="100" cy="90" r="50" stroke="rgba(201,168,76,0.1)" strokeWidth="1" fill="none"/>
        <circle cx="100" cy="90" r="35" stroke="rgba(201,168,76,0.07)" strokeWidth="0.5" fill="none"/>
        <ellipse cx="100" cy="82" rx="20" ry="24" fill="rgba(201,168,76,0.06)"/>
        <rect x="80" y="82" width="40" height="18" fill="rgba(201,168,76,0.06)"/>
        <path d="M80,100 Q85,108 90,100 Q95,108 100,100 Q105,108 110,100 Q115,108 120,100 L120,100 L80,100 Z" fill="rgba(201,168,76,0.06)"/>
        <circle cx="93" cy="79" r="3" fill="rgba(201,168,76,0.25)"/>
        <circle cx="107" cy="79" r="3" fill="rgba(201,168,76,0.25)"/>
      </>}
      {s===1&&<>
        <path d="M100,40 L130,110 L70,110 Z" stroke="rgba(201,168,76,0.15)" strokeWidth="1" fill="rgba(201,168,76,0.04)"/>
        <path d="M100,60 L120,100 L80,100 Z" stroke="rgba(201,168,76,0.1)" strokeWidth="0.5" fill="rgba(201,168,76,0.03)"/>
        <circle cx="100" cy="150" r="8" fill="rgba(201,168,76,0.08)"/>
      </>}
      {s===2&&<>
        {radials.map((r,i)=><line key={i} x1="100" y1="100" x2={r.x2} y2={r.y2} stroke="rgba(201,168,76,0.06)" strokeWidth="0.5"/>)}
        <circle cx="100" cy="100" r="15" stroke="rgba(201,168,76,0.12)" strokeWidth="1" fill="rgba(201,168,76,0.04)"/>
      </>}
      {s===3&&<>
        <path d="M40,150 Q60,100 80,120 Q100,60 120,80 Q140,40 160,90" stroke="rgba(201,168,76,0.2)" strokeWidth="1.5" fill="none"/>
        <path d="M40,160 Q60,110 80,130 Q100,70 120,90 Q140,50 160,100" stroke="rgba(201,168,76,0.08)" strokeWidth="0.5" fill="none"/>
        <circle cx="100" cy="80" r="20" stroke="rgba(201,168,76,0.1)" strokeWidth="0.5" fill="rgba(201,168,76,0.03)"/>
      </>}
      <text x="100" y="180" textAnchor="middle" fontFamily="serif" fontSize="7" fill="rgba(201,168,76,0.35)" letterSpacing="3">{item.state.toUpperCase()}</text>
      <text x="100" y="192" textAnchor="middle" fontFamily="serif" fontSize="5.5" fill="rgba(201,168,76,0.2)" letterSpacing="1">{item.cryptid.toUpperCase()}</text>
    </svg>
  );
}

function VideoThumbSVG({item}) {
  const bgs=['#1a1208','#0d1a12','#1a0d0d','#0d0d1a','#121a0d','#1a120d'];
  const bg=bgs[item.id%bgs.length];
  return (
    <svg viewBox="0 0 160 90" width="100%" height="100%" xmlns="http://www.w3.org/2000/svg" style={{position:'absolute',inset:0}}>
      <rect width="160" height="90" fill={bg}/>
      <ellipse cx="80" cy="38" rx="20" ry="24" fill="rgba(201,168,76,0.05)"/>
      <rect x="60" y="38" width="40" height="16" fill="rgba(201,168,76,0.05)"/>
      <path d="M60,54 Q65,60 70,54 Q75,60 80,54 Q85,60 90,54 Q95,60 100,54 L100,54 L60,54 Z" fill="rgba(201,168,76,0.05)"/>
      <circle cx="74" cy="35" r="3" fill="rgba(201,168,76,0.15)"/>
      <circle cx="86" cy="35" r="3" fill="rgba(201,168,76,0.15)"/>
    </svg>
  );
}

function PodcastAlbumSVG({ep}) {
  const n = ep||1;
  const rs = Array.from({length:12},(_,i)=>{
    const a=(i/12)*Math.PI*2;
    return {x2:100+Math.cos(a)*70,y2:100+Math.sin(a)*70};
  });
  return (
    <svg viewBox="0 0 200 200" width="100%" height="100%" xmlns="http://www.w3.org/2000/svg">
      <rect width="200" height="200" fill="#0d0c0a"/>
      {rs.map((r,i)=><line key={i} x1="100" y1="100" x2={r.x2} y2={r.y2} stroke="rgba(201,168,76,0.06)" strokeWidth="0.5"/>)}
      <circle cx="100" cy="100" r="70" stroke="rgba(201,168,76,0.08)" strokeWidth="0.5" fill="none"/>
      <circle cx="100" cy="100" r="50" stroke="rgba(201,168,76,0.06)" strokeWidth="0.5" fill="none"/>
      <circle cx="100" cy="100" r="30" stroke="rgba(201,168,76,0.06)" strokeWidth="0.5" fill="none"/>
      <ellipse cx="100" cy="88" rx="24" ry="28" fill="rgba(201,168,76,0.06)"/>
      <rect x="76" y="88" width="48" height="20" fill="rgba(201,168,76,0.06)"/>
      <path d="M76,108 Q81,116 86,108 Q91,116 96,108 Q101,116 106,108 Q111,116 116,108 Q121,116 124,108 L124,108 L76,108 Z" fill="rgba(201,168,76,0.06)"/>
      <circle cx="92" cy="84" r="4" fill="rgba(201,168,76,0.2)"/>
      <circle cx="108" cy="84" r="4" fill="rgba(201,168,76,0.2)"/>
      <text x="100" y="158" textAnchor="middle" fontFamily="serif" fontSize="6" fill="rgba(201,168,76,0.5)" letterSpacing="2">DON'T POKE THE GHOSTS</text>
      <text x="100" y="170" textAnchor="middle" fontFamily="serif" fontSize="5" fill="rgba(201,168,76,0.3)" letterSpacing="1">{"EP. "+String(n).padStart(2,'0')}</text>
    </svg>
  );
}

/* ============================================================
   HOME PAGE
============================================================ */
function HomePage({nav}) {
  const features = [
    {label:'Cryptid Encounters',rotate:0,desc:"From the White Thang of Alabama to the Mogollon Monster of Arizona — every state harbors something that shouldn't exist."},
    {label:'Urban Legends',rotate:15,desc:"Haunted bridges, cursed playgrounds, wishing shrines. The stories communities keep telling for a reason."},
    {label:'Expert Guidance',rotate:-10,desc:"Your host — a pagan witch and cryptid scholar — delivers history, cultural context, and actual protective advice."},
    {label:'One State at a Time',rotate:8,desc:"50 episodes. 50 states. Monthly. Every locale, every legend, every warning you didn't know you needed."},
  ];
  const stats = [['50','States Covered'],['100+','Cryptids & Legends'],['Monthly','New Episodes'],['One Host','Infinite Folklore']];

  return (
    <div>
      {/* Hero */}
      <section className="hh">
        <p className="hte">A 50-State Supernatural Podcast</p>
        <h1 className="ht">Don't Poke<br/><span className="gw">the Ghosts</span></h1>
        <p className="hd">One host. One pagan witch expert in cryptids and folklore. Fifty states worth of things that go bump in the night — and the cultural history of why they do it.</p>
        <div className="hc">
          <button className="btn" onClick={()=>nav('listen')}>Start Listening</button>
          <button className="btn btng" onClick={()=>nav('transcripts')}>Read Transcripts</button>
        </div>
      </section>

      {/* About */}
      <section style={{background:'var(--bg2)',borderBottom:'1px solid var(--b)',padding:'3rem 1.5rem'}}>
        <div className="ctr">
          <div style={{display:'grid',gridTemplateColumns:'1fr 1fr',gap:'4rem',alignItems:'center'}} className="ab2c">
            <div>
              <span className="ey">About the Show</span>
              <h2 style={{fontSize:'clamp(1.4rem,3vw,2rem)',marginBottom:'1rem'}}>Where folklore meets field work</h2>
              <p style={{color:'var(--tm)',marginBottom:'1rem',fontSize:'.95rem'}}>Each episode, a guest contacts the host — a pagan witch with deep expertise in cryptids and supernatural folklore — about something they can't explain. A creature in the woods. A bridge that doesn't feel right. A legend their grandmother swore was true.</p>
              <p style={{color:'var(--tm)',fontSize:'.95rem'}}>The host delivers: the history, the cultural context, the documented sightings, and — crucially — what you should actually <em>do</em> about it. Educational, irreverent, and occasionally alarming.</p>
            </div>
            <div style={{display:'flex',flexDirection:'column',gap:'.1rem'}}>
              {stats.map(([n,l])=>(
                <div key={l} style={{display:'flex',justifyContent:'space-between',alignItems:'baseline',padding:'.75rem 0',borderBottom:'1px solid var(--b)'}}>
                  <span style={{fontFamily:'Cinzel,serif',fontSize:'1.5rem',fontWeight:900,color:'var(--gold)'}}>{n}</span>
                  <span style={{fontFamily:'Cinzel,serif',fontSize:'.68rem',letterSpacing:'.15em',textTransform:'uppercase',color:'var(--tm)'}}>{l}</span>
                </div>
              ))}
            </div>
          </div>
        </div>
      </section>

      {/* Features */}
      <section style={{padding:'4rem 1.5rem',borderBottom:'1px solid var(--b)'}}>
        <div className="ctr">
          <div style={{textAlign:'center',marginBottom:'3rem'}}>
            <span className="ey">What to Expect</span>
            <h2 style={{fontSize:'clamp(1.4rem,3vw,2rem)'}}>Every episode has two segments</h2>
          </div>
          <div className="g2">
            {features.map(f=>(
              <div key={f.label} style={{background:'var(--bg)',padding:'2.5rem 2rem'}}>
                <div style={{marginBottom:'1rem'}}><Planchette size={34} color="var(--gold)" opacity={0.65} rotate={f.rotate||0}/></div>
                <div className="sl">{f.label}</div>
                <p style={{color:'var(--tm)',fontSize:'.9rem',marginTop:'.5rem'}}>{f.desc}</p>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* State grid */}
      <section style={{padding:'4rem 1.5rem',borderBottom:'1px solid var(--b)',background:'var(--bg2)'}}>
        <div className="ctr">
          <span className="ey">The Full Map</span>
          <h2 style={{fontSize:'clamp(1.4rem,3vw,2rem)',marginBottom:'.5rem'}}>All 50 States. Every Legend.</h2>
          <p style={{color:'var(--tm)',fontSize:'.9rem',marginBottom:'2rem'}}>One episode per state. Click a state to explore its transcript.</p>
          <div style={{display:'flex',flexWrap:'wrap',gap:'.4rem'}}>
            {STATES.map(s=>(
              <StateBtn key={s} abbr={s} onClick={()=>nav('transcripts')}/>
            ))}
          </div>
        </div>
      </section>

      {/* Quote */}
      <section style={{padding:'4rem 1.5rem',borderBottom:'1px solid var(--b)'}}>
        <div className="ctrn">
          <div className="dv"><Planchette size={16} color="var(--gold)" opacity={0.45}/></div>
          <blockquote style={{fontFamily:'IM Fell English,Georgia,serif',fontStyle:'italic',fontSize:'clamp(1.2rem,2.5vw,1.6rem)',color:'var(--t)',lineHeight:1.5,textAlign:'center',margin:'0 0 2rem'}}>
            "Salt is not folk superstition — it's protective magic with a very long resume."
          </blockquote>
          <p style={{textAlign:'center',color:'var(--tm)',fontFamily:'Cinzel,serif',fontSize:'.7rem',letterSpacing:'.15em'}}>— The Host, Episode 1: Alabama</p>
          <div className="dv"><Planchette size={16} color="var(--gold)" opacity={0.45}/></div>
        </div>
      </section>

      {/* CTA */}
      <section style={{padding:'4rem 1.5rem',textAlign:'center'}}>
        <div className="ctrn">
          <span className="ey">New Episodes Monthly</span>
          <h2 style={{fontSize:'clamp(1.4rem,3vw,2rem)',marginBottom:'1rem'}}>Ready to not poke the ghosts?</h2>
          <p style={{color:'var(--tm)',marginBottom:'2rem',fontSize:'.95rem'}}>Find every episode, full transcripts, source materials, and the art that brought it all to life.</p>
          <div style={{display:'flex',gap:'1rem',justifyContent:'center',flexWrap:'wrap'}}>
            <button className="btn" onClick={()=>nav('listen')}>Listen Now</button>
            <button className="btn btng" onClick={()=>nav('videos')}>Watch Videos</button>
            <button className="btn btng" onClick={()=>nav('sources')}>Sources & Resources</button>
          </div>
        </div>
      </section>
    </div>
  );
}

function StateBtn({abbr,onClick}) {
  const [hov,setHov] = useState(false);
  return (
    <button
      onClick={onClick}
      onMouseEnter={()=>setHov(true)}
      onMouseLeave={()=>setHov(false)}
      style={{
        width:'3rem',height:'3rem',
        border:`1px solid ${hov?'var(--gold)':'var(--b)'}`,
        background:hov?'rgba(201,168,76,0.05)':'var(--bgc)',
        color:hov?'var(--gold)':'var(--tm)',
        fontFamily:'Cinzel,serif',fontSize:'.55rem',letterSpacing:'.05em',
        cursor:'pointer',transition:'all .15s',
        display:'flex',alignItems:'center',justifyContent:'center',
      }}
    >{abbr}</button>
  );
}

/* ============================================================
   VIDEOS PAGE
============================================================ */
function VideosPage() {
  const [filter,setFilter] = useState('All');
  const [playing,setPlaying] = useState(null);
  const filtered = filter==='All' ? VIDEO_LIST : VIDEO_LIST.filter(v=>v.type===filter);

  return (
    <div>
      <div className="ph">
        <div className="ctr">
          <span className="ey">Visual Content</span>
          <h1 className="pt">Videos</h1>
          <p className="ps">Full episode recordings, clips, and bonus visual content from the field.</p>
        </div>
      </div>
      <div className="ctr" style={{padding:'2.5rem 1.5rem'}}>
        {/* Filter */}
        <div style={{display:'flex',gap:'.5rem',marginBottom:'2.5rem',flexWrap:'wrap',alignItems:'center'}}>
          <span style={{fontFamily:'Cinzel,serif',fontSize:'.65rem',letterSpacing:'.2em',color:'var(--td)',textTransform:'uppercase',marginRight:'.5rem'}}>Filter:</span>
          {['All','Cryptid','Urban Legend'].map(opt=>(
            <FilterBtn key={opt} label={opt} active={filter===opt} onClick={()=>setFilter(opt)}/>
          ))}
        </div>

        {/* Grid */}
        <div className="g3">
          {filtered.map(v=>(
            <div key={v.id} className="vt" onClick={()=>setPlaying(playing===v.id?null:v.id)}>
              <div className="vti">
                <VideoThumbSVG item={v}/>
                <div className="vpo">
                  <div className="vpl"><Planchette size={22} color="var(--gold)" opacity={1} rotate={playing===v.id?15:0}/></div>
                </div>
                <div style={{position:'absolute',bottom:'.5rem',right:'.5rem',background:'rgba(13,12,10,.8)',fontFamily:'Cinzel,serif',fontSize:'.6rem',color:'var(--tm)',padding:'.1rem .4rem'}}>{v.dur}</div>
              </div>
              {playing===v.id&&(
                <div style={{background:'var(--bg2)',padding:'.75rem 1rem',borderTop:'1px solid var(--b)'}}>
                  <div style={{display:'flex',alignItems:'center',gap:'1rem',marginBottom:'.5rem'}}>
                    <button className="pb" onClick={e=>{e.stopPropagation();setPlaying(null)}} style={{width:'2rem',height:'2rem'}}><Planchette size={16} color="var(--gold)" opacity={1} rotate={15}/></button>
                    <div className="prg"><div className="prf" style={{width:'30%'}}/></div>
                    <span style={{fontFamily:'Cinzel,serif',fontSize:'.6rem',color:'var(--td)',whiteSpace:'nowrap'}}>12:44 / {v.dur}</span>
                  </div>
                  <p style={{fontSize:'.75rem',color:'var(--td)',fontStyle:'italic'}}>Add your video embed URL to enable playback.</p>
                </div>
              )}
              <div style={{padding:'1rem'}}>
                <div style={{display:'flex',justifyContent:'space-between',alignItems:'center',marginBottom:'.4rem'}}>
                  <span className="ep">Ep. {String(v.ep).padStart(2,'0')}</span>
                  <span className={`tag${v.type==='Urban Legend'?' tm2':''}`}>{v.type}</span>
                </div>
                <div style={{fontFamily:'Cinzel,serif',fontSize:'.9rem',fontWeight:600,color:'var(--t)',marginBottom:'.2rem'}}>{v.title}</div>
                <div style={{fontFamily:'Cinzel,serif',fontSize:'.62rem',letterSpacing:'.1em',color:'var(--tm)',textTransform:'uppercase'}}>{v.state}</div>
              </div>
            </div>
          ))}
        </div>

        <div style={{marginTop:'3rem',padding:'2rem',border:'1px solid var(--b)',background:'var(--bgc)',textAlign:'center'}}>
          <div className="sl" style={{marginBottom:'.75rem'}}>Add Your Videos</div>
          <p style={{color:'var(--tm)',fontSize:'.9rem',maxWidth:'500px',margin:'0 auto'}}>Upload video files or paste YouTube/Vimeo embed links to populate this page with your actual episode recordings.</p>
        </div>
      </div>
    </div>
  );
}

function FilterBtn({label,active,onClick}) {
  return (
    <button onClick={onClick} style={{
      fontFamily:'Cinzel,serif',fontSize:'.65rem',letterSpacing:'.12em',textTransform:'uppercase',
      padding:'.35rem .9rem',
      border:`1px solid ${active?'var(--gold)':'var(--b)'}`,
      color:active?'var(--gold)':'var(--tm)',
      background:active?'var(--goldd)':'transparent',
      cursor:'pointer',transition:'all .15s',
    }}>{label}</button>
  );
}

/* ============================================================
   TRANSCRIPTS PAGE
============================================================ */
function TranscriptsPage() {
  const [selEp,setSelEp] = useState(0);
  const [selSeg,setSelSeg] = useState(0);
  const [search,setSearch] = useState('');

  const filtered = search.trim()
    ? EPISODES.filter(e=>e.state.toLowerCase().includes(search.toLowerCase())||e.segments.some(s=>s.title.toLowerCase().includes(search.toLowerCase())||s.guest.toLowerCase().includes(search.toLowerCase())))
    : EPISODES;

  const curEp = EPISODES[selEp];
  const curSeg = curEp?.segments[selSeg];

  return (
    <div>
      <div className="ph">
        <div className="ctr">
          <span className="ey">Episode Transcripts</span>
          <h1 className="pt">Transcripts</h1>
          <p className="ps">Full transcripts for every episode. Search by state, cryptid, or guest name.</p>
        </div>
      </div>
      <div className="ctr" style={{padding:'2.5rem 1.5rem'}}>
        <div style={{marginBottom:'2rem',maxWidth:'420px'}}>
          <input className="inp" type="text" placeholder="Search by state, cryptid, or guest..." value={search} onChange={e=>setSearch(e.target.value)}/>
        </div>

        <div className="tv">
          {/* Sidebar */}
          <div className="ts">
            {(search?filtered:EPISODES).map(ep=>(
              <button key={ep.ep} className={`tsi${selEp===EPISODES.indexOf(ep)?' act':''}`}
                onClick={()=>{setSelEp(EPISODES.indexOf(ep));setSelSeg(0)}}>
                <div className="ep">Episode {String(ep.ep).padStart(2,'0')}</div>
                <div style={{fontFamily:'Cinzel,serif',fontSize:'.85rem',fontWeight:600,color:'var(--t)',marginTop:'.2rem'}}>{ep.state}</div>
                <div style={{fontSize:'.75rem',color:'var(--td)',marginTop:'.2rem'}}>{ep.segments.length} segment{ep.segments.length>1?'s':''}</div>
              </button>
            ))}
            {filtered.length===0&&<div style={{padding:'2rem 1rem',color:'var(--td)',fontSize:'.85rem',fontStyle:'italic'}}>No episodes match your search.</div>}
          </div>

          {/* Content */}
          <div className="tc">
            {curEp&&<>
              {/* Segment tabs */}
              <div style={{display:'flex',borderBottom:'1px solid var(--b)',background:'var(--bg2)',marginBottom:'0'}}>
                {curEp.segments.map((seg,i)=>(
                  <button key={i} onClick={()=>setSelSeg(i)} style={{
                    fontFamily:'Cinzel,serif',fontSize:'.62rem',letterSpacing:'.12em',textTransform:'uppercase',
                    padding:'.75rem 1.25rem',border:'none',
                    borderBottom:selSeg===i?'2px solid var(--gold)':'2px solid transparent',
                    background:'transparent',
                    color:selSeg===i?'var(--gold)':'var(--tm)',
                    cursor:'pointer',transition:'color .15s',
                  }}>{seg.type}</button>
                ))}
              </div>

              {curSeg&&<div style={{padding:'2rem'}}>
                <div style={{marginBottom:'1.5rem'}}>
                  <div style={{display:'flex',gap:'.5rem',marginBottom:'.75rem',flexWrap:'wrap'}}>
                    <span className={`tag${curSeg.type==='Urban Legend'?' tm2':''}`}>{curSeg.type}</span>
                    <span className="ep" style={{alignSelf:'center'}}>Ep. {String(curEp.ep).padStart(2,'0')} — {curEp.state}</span>
                  </div>
                  <h2 style={{fontSize:'1.5rem',marginBottom:'.5rem'}}>{curSeg.title}</h2>
                  <div style={{fontFamily:'Cinzel,serif',fontSize:'.68rem',letterSpacing:'.12em',color:'var(--tm)',textTransform:'uppercase',marginBottom:'.75rem'}}>Guest: {curSeg.guest}</div>
                  <p style={{color:'var(--tm)',fontSize:'.9rem',fontStyle:'italic',borderLeft:'2px solid var(--bm)',paddingLeft:'1rem'}}>{curSeg.premise}</p>
                </div>
                <div className="dv"><Planchette size={16} color="var(--gold)" opacity={0.45}/></div>
                <div>
                  {curSeg.lines.map((line,i)=>(
                    <div key={i} style={{marginBottom:'1.5rem'}}>
                      <div style={{fontFamily:'Cinzel,serif',fontSize:'.62rem',letterSpacing:'.2em',textTransform:'uppercase',color:line.spk==='Host'?'var(--gold)':'var(--moss)',marginBottom:'.3rem'}}>{line.spk}</div>
                      <p style={{fontSize:'.95rem',lineHeight:'1.85',color:'var(--t)'}}>{line.t}</p>
                    </div>
                  ))}
                  <div style={{marginTop:'2rem',padding:'1rem',background:'var(--bg2)',border:'1px solid var(--b)',fontSize:'.8rem',color:'var(--td)',fontStyle:'italic'}}>
                    This is an excerpt. Full episode transcripts available in the complete archive.
                  </div>
                </div>
              </div>}
            </>}
            {!curEp&&<div style={{display:'flex',alignItems:'center',justifyContent:'center',height:'100%',color:'var(--td)',fontStyle:'italic'}}>Select an episode to read its transcript.</div>}
          </div>
        </div>

        <div style={{marginTop:'2rem',display:'flex',justifyContent:'space-between',alignItems:'center',flexWrap:'wrap',gap:'1rem'}}>
          <p style={{color:'var(--tm)',fontSize:'.85rem'}}>Full transcripts for all 50 episodes available in the complete archive.</p>
          <button className="btn">Download All Transcripts</button>
        </div>
      </div>
    </div>
  );
}

/* ============================================================
   LISTEN PAGE
============================================================ */
function ListenPage() {
  const [activeEp,setActiveEp] = useState(1);
  const [playing,setPlaying] = useState(false);
  const [progress,setProgress] = useState(0);
  const curEp = EPISODES.find(e=>e.ep===activeEp);

  function handleProgress(e) {
    const rect = e.currentTarget.getBoundingClientRect();
    setProgress(((e.clientX-rect.left)/rect.width)*100);
  }

  function prevEp() {
    const i=EPISODES.findIndex(e=>e.ep===activeEp);
    if(i>0){setActiveEp(EPISODES[i-1].ep);setProgress(0);setPlaying(false)}
  }
  function nextEp() {
    const i=EPISODES.findIndex(e=>e.ep===activeEp);
    if(i<EPISODES.length-1){setActiveEp(EPISODES[i+1].ep);setProgress(0);setPlaying(false)}
  }

  return (
    <div>
      <div className="ph">
        <div className="ctr">
          <span className="ey">Audio Episodes</span>
          <h1 className="pt">Listen</h1>
          <p className="ps">Every episode, every state. Stream directly or subscribe on your platform of choice.</p>
        </div>
      </div>
      <div className="ctr" style={{padding:'2.5rem 1.5rem'}}>
        {/* Platforms */}
        <div style={{marginBottom:'3rem'}}>
          <div className="sl" style={{marginBottom:'1rem'}}>Subscribe & Stream</div>
          <div style={{display:'flex',gap:'.75rem',flexWrap:'wrap'}}>
            {PLATFORMS.map(p=><PlatformBtn key={p.name} p={p}/>)}
          </div>
        </div>

        {/* Player + list */}
        <div style={{display:'grid',gridTemplateColumns:'1fr 340px',gap:'1px',background:'var(--b)',alignItems:'start'}} className="ab2c">
          {/* Episode list */}
          <div style={{background:'var(--bg)'}}>
            {EPISODES.map(ep=>(
              <EpListItem key={ep.ep} ep={ep} active={activeEp===ep.ep} playing={playing}
                onClick={()=>{setActiveEp(ep.ep);setPlaying(false);setProgress(0)}}/>
            ))}
            <div style={{padding:'1rem 1.25rem',color:'var(--td)',fontSize:'.8rem',fontStyle:'italic',borderBottom:'1px solid var(--b)'}}>+ 46 more episodes — subscribe to access the full archive</div>
          </div>

          {/* Player */}
          <div style={{background:'var(--bg2)',position:'sticky',top:'65px',padding:'1.5rem',borderLeft:'1px solid var(--b)'}}>
            {curEp&&<>
              <div style={{width:'100%',aspectRatio:'1',background:'var(--bgc)',border:'1px solid var(--b)',marginBottom:'1.25rem',overflow:'hidden'}}>
                <PodcastAlbumSVG ep={curEp.ep}/>
              </div>
              <div className="ep" style={{marginBottom:'.3rem'}}>Episode {String(curEp.ep).padStart(2,'0')} — {curEp.state}</div>
              <div style={{fontFamily:'Cinzel,serif',fontSize:'.95rem',fontWeight:600,color:'var(--t)',marginBottom:'1.25rem',lineHeight:1.3}}>{curEp.segments[0].title}</div>
              <div className="prg" style={{marginBottom:'.6rem'}} onClick={handleProgress}>
                <div className="prf" style={{width:`${progress}%`}}/>
              </div>
              <div style={{display:'flex',justifyContent:'space-between',fontFamily:'Cinzel,serif',fontSize:'.6rem',color:'var(--td)',marginBottom:'1rem'}}>
                <span>0:00</span><span>{curEp.duration}</span>
              </div>
              <div style={{display:'flex',alignItems:'center',justifyContent:'center',gap:'.75rem'}}>
                <button onClick={prevEp} style={{border:'none',background:'none',color:'var(--tm)',cursor:'pointer',padding:'.25rem',display:'flex'}}><Planchette size={22} color="var(--tm)" opacity={0.7} rotate={-90}/></button>
                <button className="pb" style={{width:'3rem',height:'3rem'}} onClick={()=>setPlaying(p=>!p)}><Planchette size={22} color="var(--gold)" opacity={1} rotate={playing?15:0}/></button>
                <button onClick={nextEp} style={{border:'none',background:'none',color:'var(--tm)',cursor:'pointer',padding:'.25rem',display:'flex'}}><Planchette size={22} color="var(--tm)" opacity={0.7} rotate={90}/></button>
              </div>
              <p style={{textAlign:'center',fontSize:'.72rem',color:'var(--td)',marginTop:'1.25rem',fontStyle:'italic'}}>Add your audio files or podcast embed URL to enable playback.</p>
            </>}
          </div>
        </div>
      </div>
    </div>
  );
}

function PlatformBtn({p}) {
  const [hov,setHov]=useState(false);
  return (
    <button onMouseEnter={()=>setHov(true)} onMouseLeave={()=>setHov(false)} style={{
      display:'flex',alignItems:'center',gap:'.6rem',
      padding:'.6rem 1.1rem',
      border:`1px solid ${hov?p.col:'var(--bm)'}`,
      color:hov?p.col:'var(--tm)',
      fontFamily:'Cinzel,serif',fontSize:'.68rem',letterSpacing:'.1em',textTransform:'uppercase',
      background:'transparent',cursor:'pointer',transition:'border-color .15s,color .15s',
    }}>
      <Planchette size={18} color="currentColor" opacity={0.8}/>{p.name}
    </button>
  );
}

function EpListItem({ep,active,playing,onClick}) {
  const [hov,setHov]=useState(false);
  return (
    <button onClick={onClick}
      onMouseEnter={()=>setHov(true)} onMouseLeave={()=>setHov(false)}
      style={{
        display:'flex',alignItems:'center',gap:'1rem',width:'100%',
        padding:'1rem 1.25rem',borderBottom:'1px solid var(--b)',cursor:'pointer',
        background:active?'var(--bgh)':hov?'var(--bg2)':'var(--bg)',
        borderLeft:active?'2px solid var(--gold)':'2px solid transparent',
        transition:'background .15s',font:'inherit',color:'inherit',textAlign:'left',
      }}>
      <div style={{width:'2rem',height:'2rem',flexShrink:0,display:'flex',alignItems:'center',justifyContent:'center',
        border:`1px solid ${active?'var(--gold)':'var(--bm)'}`,
        color:active?'var(--gold)':'var(--td)',fontFamily:'Cinzel,serif',fontSize:'.65rem'}}>
        {active&&playing?<Planchette size={16} color="var(--gold)" opacity={1} rotate={0}/>:String(ep.ep).padStart(2,'0')}
      </div>
      <div style={{flex:1,minWidth:0}}>
        <div style={{fontFamily:'Cinzel,serif',fontSize:'.62rem',letterSpacing:'.12em',color:'var(--td)',textTransform:'uppercase',marginBottom:'.2rem'}}>{ep.state} — {ep.date}</div>
        <div style={{fontFamily:'Lora,serif',fontSize:'.9rem',color:'var(--t)',whiteSpace:'nowrap',overflow:'hidden',textOverflow:'ellipsis'}}>{ep.segments[0].title}</div>
      </div>
      <span style={{fontFamily:'Cinzel,serif',fontSize:'.6rem',color:'var(--td)',flexShrink:0}}>{ep.duration}</span>
    </button>
  );
}

/* ============================================================
   SOURCES PAGE
============================================================ */
const TYPE_COLS = {Book:'var(--gold)',Website:'var(--moss)',Film:'var(--rust)',Database:'var(--moss)',Organization:'var(--tm)',Archive:'var(--tm)',Report:'var(--tm)',News:'var(--tm)','Historic Record':'var(--gold)','Cultural Record':'var(--gold)',Academic:'var(--gold)'};

function SourcesPage() {
  const [activeState,setActiveState]=useState('All');
  const [typeFilter,setTypeFilter]=useState('All');
  const [search,setSearch]=useState('');

  const stateOptions=['All',...SOURCES.map(s=>s.state)];
  const visible = SOURCES
    .filter(s=>activeState==='All'||s.state===activeState)
    .map(s=>({...s,items:s.items.filter(item=>{
      const mt=typeFilter==='All'||item.type===typeFilter;
      const ms=!search.trim()||item.cit.toLowerCase().includes(search.toLowerCase());
      return mt&&ms;
    })}))
    .filter(s=>s.items.length>0);

  return (
    <div>
      <div className="ph">
        <div className="ctr">
          <span className="ey">Bibliography & Further Reading</span>
          <h1 className="pt">Sources & Resources</h1>
          <p className="ps">Every citation, database, archive, and cultural record referenced across all 50 episodes.</p>
        </div>
      </div>
      <div className="ctr" style={{padding:'2.5rem 1.5rem'}}>
        {/* Controls */}
        <div style={{display:'flex',gap:'1rem',flexWrap:'wrap',marginBottom:'2.5rem',alignItems:'flex-end'}}>
          <div style={{flex:'1 1 240px'}}>
            <div className="sl" style={{marginBottom:'.4rem'}}>Search</div>
            <input className="inp" type="text" placeholder="Search by author, title, or keyword..." value={search} onChange={e=>setSearch(e.target.value)}/>
          </div>
          <div>
            <div className="sl" style={{marginBottom:'.4rem'}}>Source Type</div>
            <div style={{display:'flex',gap:'.4rem',flexWrap:'wrap'}}>
              {['All','Book','Website','Film','Database','Historic Record','Academic'].map(t=>(
                <FilterBtn key={t} label={t} active={typeFilter===t} onClick={()=>setTypeFilter(t)}/>
              ))}
            </div>
          </div>
        </div>

        {/* State tabs */}
        <div style={{display:'flex',overflowX:'auto',borderBottom:'1px solid var(--b)',marginBottom:'2.5rem'}}>
          {stateOptions.map(s=>(
            <button key={s} onClick={()=>setActiveState(s)} style={{
              fontFamily:'Cinzel,serif',fontSize:'.6rem',letterSpacing:'.1em',textTransform:'uppercase',
              padding:'.6rem 1rem',border:'none',
              borderBottom:activeState===s?'2px solid var(--gold)':'2px solid transparent',
              color:activeState===s?'var(--gold)':'var(--td)',
              background:'transparent',cursor:'pointer',whiteSpace:'nowrap',transition:'color .15s',
            }}>{s}</button>
          ))}
        </div>

        {visible.length===0?(
          <div style={{padding:'3rem',textAlign:'center',color:'var(--td)',fontStyle:'italic'}}>No sources match your filters.</div>
        ):visible.map(section=>(
          <div key={section.state} style={{marginBottom:'3rem'}}>
            <div style={{display:'flex',alignItems:'baseline',gap:'1rem',marginBottom:'1rem'}}>
              <h2 style={{fontSize:'1.1rem'}}>{section.state}</h2>
              {section.ep>0&&<span className="ep">Episode {String(section.ep).padStart(2,'0')}</span>}
            </div>
            <div style={{paddingLeft:'1rem',borderLeft:'1px solid var(--b)'}}>
              {section.items.map((item,i)=>(
                <div key={i} className="si">
                  <span style={{fontFamily:'Cinzel,serif',fontSize:'.58rem',letterSpacing:'.1em',textTransform:'uppercase',
                    color:TYPE_COLS[item.type]||'var(--td)',
                    border:`1px solid ${TYPE_COLS[item.type]||'var(--b)'}`,
                    padding:'.1rem .4rem',flexShrink:0,marginTop:'.15rem'}}>
                    {item.type}
                  </span>
                  <p style={{fontSize:'.9rem',color:'var(--tm)',lineHeight:1.6,margin:0}}>{item.cit}</p>
                </div>
              ))}
            </div>
          </div>
        ))}

        {/* Resources */}
        <div className="dv"><Planchette size={16} color="var(--gold)" opacity={0.45}/></div>
        <div>
          <h2 style={{fontSize:'1.1rem',marginBottom:'1.5rem'}}>Recommended Further Reading</h2>
          <div className="g3">
            {[
              {title:'American Folklore Society',desc:'Academic folklore research and state-by-state legend archives.',url:'https://www.afsnet.org'},
              {title:'Bigfoot Field Researchers Organization',desc:'Sighting database, field reports, and investigation methodology.',url:'https://www.bfro.net'},
              {title:'Atlas Obscura',desc:'Curated database of unusual, hidden, and strange places across the United States.',url:'https://www.atlasobscura.com'},
              {title:'Cryptomundo',desc:'Cryptozoology news, analysis, and community forum.',url:'https://cryptomundo.com'},
              {title:'Fortean Times',desc:'Long-running journal documenting anomalous phenomena worldwide.',url:'https://www.forteantimes.com'},
              {title:'Paranormal Encyclopedia',desc:'Cross-cultural reference for supernatural entities, traditions, and folklore.',url:'#'},
            ].map(r=>(
              <div key={r.title} className="card">
                <div style={{fontFamily:'Cinzel,serif',fontSize:'.85rem',fontWeight:600,color:'var(--t)',marginBottom:'.5rem'}}>{r.title}</div>
                <p style={{fontSize:'.82rem',color:'var(--tm)',marginBottom:'.75rem'}}>{r.desc}</p>
                <a href={r.url} className="btn" style={{fontSize:'.6rem',padding:'.4rem .8rem',display:'inline-flex',alignItems:'center',gap:'.4rem'}} target="_blank" rel="noopener noreferrer"><Planchette size={12} color="currentColor" opacity={1} rotate={45}/>Visit</a>
              </div>
            ))}
          </div>
        </div>

        {/* ── PROTECTIONS AGAINST THE SUPERNATURAL ── */}
        <div className="dv"><Planchette size={16} color="var(--gold)" opacity={0.45}/></div>

        <div style={{marginBottom:'3rem'}}>
          <span className="ey">Field Guide</span>
          <h2 style={{fontSize:'clamp(1.4rem,3vw,2rem)',marginBottom:'.5rem'}}>Protections Against the Supernatural</h2>
          <p style={{color:'var(--tm)',fontSize:'.95rem',maxWidth:'660px',fontFamily:'IM Fell English,Georgia,serif',fontStyle:'italic',lineHeight:1.7}}>
            "The most common mistake people make is waiting until something is wrong to start protecting themselves. Protection is maintenance, not emergency response."
          </p>
          <p style={{color:'var(--td)',fontSize:'.75rem',fontFamily:'Cinzel,serif',letterSpacing:'.1em',marginTop:'.5rem'}}>— The Host, recurring advice across all 50 episodes</p>
        </div>

        {/* Category grid */}
        {[
          {
            cat: 'Threshold & Boundary',
            rotate: 0,
            desc: 'The threshold is the most important line in any protective practice. What you allow to cross it defines what you live with.',
            items: [
              {
                name: 'Salt Lines',
                strength: 'Essential',
                col: 'var(--gold)',
                body: 'Pour an unbroken line of salt across every threshold — doors, windows, and any opening to the outside. Table salt works. Sea salt works better. Do not let anyone scoff at you for it.',
                source: 'Cross-cultural practice documented across European, African, Asian, and Indigenous American traditions. Referenced in nearly every episode.',
              },
              {
                name: 'Iron at the Entry',
                strength: 'Essential',
                col: 'var(--gold)',
                body: 'Iron is one of the oldest and most universal repellents in folklore. A horseshoe above the door (open end up), iron nails in the frame, or a simple iron bar across the threshold. Cold iron specifically repels the fae, certain spirits, and boundary-crossing entities.',
                source: 'Briggs, Katharine M. The Fairies in Tradition and Literature. Routledge, 1967. Also: widespread European and Indigenous traditions.',
              },
              {
                name: 'Protective Herbs Above the Door',
                strength: 'Supplementary',
                col: 'var(--moss)',
                body: 'Dried bundles of rosemary (for clarity and protection), angelica root (a powerful general ward), and mugwort (for psychic interference) hung above a doorway form a passive barrier that weakens over time and should be replaced seasonally.',
                source: 'Cunningham, Scott. Cunningham\'s Encyclopedia of Magical Herbs. Llewellyn, 1985.',
              },
              {
                name: 'Thresholds of Water',
                strength: 'Supplementary',
                col: 'var(--moss)',
                body: 'Many traditions hold that running water cannot be crossed by certain entities. A shallow pan of water at the threshold, or strategically placed bowls of water in a room, can act as a secondary barrier. Change the water regularly — stagnant water loses its protective quality and can become attractive rather than repellent.',
                source: 'Guiley, Rosemary Ellen. The Encyclopedia of Ghosts and Spirits. 3rd ed. Checkmark Books, 2007.',
              },
            ],
          },
          {
            cat: 'Personal Protection',
            rotate: -8,
            desc: 'What you carry on your body creates a mobile perimeter. These work whether you are at home or in the field.',
            items: [
              {
                name: 'Black Tourmaline',
                strength: 'Highly Recommended',
                col: 'var(--gold)',
                body: 'Worn on the body or kept in a pocket, black tourmaline is widely regarded as the most effective general-purpose protective stone. It absorbs and deflects negative energy, electromagnetic interference, and psychic intrusion. Cleanse it monthly under running water.',
                source: 'Hall, Judy. The Crystal Bible. Walking Stick Press, 2003.',
              },
              {
                name: 'Obsidian',
                strength: 'Highly Recommended',
                col: 'var(--gold)',
                body: 'Volcanic glass with a long history of use in protective and divination contexts across Mesoamerican, Pacific, and European traditions. Apache Tears (a rounded form of obsidian) are particularly valued for grief and psychic shock after a supernatural encounter.',
                source: 'Referenced in episodes covering California (Dark Watchers) and Southwest Indigenous traditions.',
              },
              {
                name: 'Protective Sachets (Mojo Bags)',
                strength: 'Recommended',
                col: 'var(--moss)',
                body: 'A small cloth bag containing a combination of protective items — salt, iron filings, a protective stone, dried herb, and a personal item. The combination matters less than the intention and the consistency of carrying it. Red for protection, black for banishing, white for general warding.',
                source: 'Yronwode, Catherine. Hoodoo Herb and Root Magic. Lucky Mojo Curio Co., 2002.',
              },
              {
                name: 'Rowan Berries & Crosses',
                strength: 'Traditional',
                col: 'var(--moss)',
                body: 'Two twigs of rowan bound with red thread into a cross is one of the oldest protective charms in the British Isles and Appalachian folk magic. Effective against witchcraft, the evil eye, and certain categories of entity. Rowan is called the "witch wood" — it takes one to know one.',
                source: 'Mooney, Thorn. Traditional Wicca. Llewellyn, 2018. Also: Appalachian folk tradition documentation.',
              },
            ],
          },
          {
            cat: 'Cleansing & Banishing',
            rotate: 12,
            desc: 'After an encounter, before you sleep in a space for the first time, and at the turn of each season. These are not one-time procedures.',
            items: [
              {
                name: 'Smoke Cleansing',
                strength: 'Essential',
                col: 'var(--gold)',
                body: 'Burning dried herbs — rosemary, cedar, and juniper are the host\'s preferred alternatives to white sage, which is a sacred and overharvested plant belonging to specific Indigenous traditions. Move clockwise through a space, paying attention to corners, closets, and mirrors. Open a window to give whatever you are displacing a way out.',
                source: 'Note: White sage (Salvia apiana) is sacred to numerous California Native peoples. Use ethically sourced materials or regional alternatives.',
              },
              {
                name: 'Sound & Bell Ringing',
                strength: 'Highly Recommended',
                col: 'var(--gold)',
                body: 'High-pitched sound disrupts and disorients entities. A hand bell rung in each corner of a room, moving clockwise, is one of the oldest cleansing methods in European and East Asian traditions. Tibetan singing bowls, brass bells, and clapping all function similarly. The human voice raised in intention also works.',
                source: 'Achterberg, Jeanne. Imagery in Healing. Shambhala, 1985. Also: Tibetan Buddhist ritual practice documentation.',
              },
              {
                name: 'Florida Water & Holy Water',
                strength: 'Recommended',
                col: 'var(--moss)',
                body: 'Spiritual colognes like Florida Water have been used in Afro-Caribbean, Spiritualist, and hoodoo traditions for over a century as a general cleanser and offering. A spritz at thresholds, on the body, or on objects brings clarity and disrupts lingering presences. Holy water functions similarly in Catholic folk practice.',
                source: 'Glassman, Sallie Ann. Vodou Visions. Villard, 2000.',
              },
              {
                name: 'Fire & Candle Work',
                strength: 'Recommended',
                col: 'var(--moss)',
                body: 'White candles burned at the four corners of a room while stating a clear protective intention. Black candles absorb and transmute negative energy. The act of burning transforms — it is one of the fundamental mechanisms of sympathetic magic, and it works whether you believe in it or not.',
                source: 'Buck, Vikki. Candle Magic for Beginners. Referenced across multiple folk magic traditions.',
              },
            ],
          },
          {
            cat: 'Binding & Containment',
            rotate: -5,
            desc: 'When you cannot banish — when something is anchored, territorial, or simply too large to move — containment is the alternative.',
            items: [
              {
                name: 'Mirrors Facing Outward',
                strength: 'Traditional',
                col: 'var(--moss)',
                body: 'A mirror placed facing outward — toward a door, a window, or a suspected point of entry — reflects whatever approaches back toward its source. This is a standard technique in Chinese Feng Shui (the bagua mirror), European folk magic, and Hoodoo. Convex mirrors are considered more effective than flat.',
                source: 'Lip, Evelyn. Feng Shui for the Home. Heian International, 1990.',
              },
              {
                name: 'Iron Circles',
                strength: 'Highly Recommended',
                col: 'var(--gold)',
                body: 'An unbroken circle of iron — nails, filings, or chain — around an object, a person, or a space creates a containment barrier that most folklore entities cannot cross. Iron filings poured in a circle around your sleeping area is an extreme but documented practice in rural British and Appalachian tradition.',
                source: 'Campbell, Joseph. The Masks of God: Primitive Mythology. Penguin, 1959.',
              },
              {
                name: 'Knot Magic & Cord Binding',
                strength: 'Traditional',
                col: 'var(--moss)',
                body: 'Tying a series of knots in a cord while stating an intention — each knot binding the entity to a specific prohibition — is documented in Norse, Slavic, and Scottish sea-witch traditions. Nine knots is the traditional count. Keep the cord; the binding holds as long as the knots do.',
                source: 'Valiente, Doreen. Natural Magic. St. Martin\'s Press, 1975.',
              },
              {
                name: 'Petition Papers & Sealed Vessels',
                strength: 'Supplementary',
                col: 'var(--moss)',
                body: 'Writing the name of an entity or a specific prohibition on paper, sealing it in a bottle or jar with binding materials (salt, rusty nails, red pepper, knotted thread), and burying it away from the home. This is a standard hoodoo technique for containing troublesome presences.',
                source: 'Yronwode, Catherine. Hoodoo Herb and Root Magic. Lucky Mojo Curio Co., 2002.',
              },
            ],
          },
          {
            cat: 'Documentation & Observation',
            rotate: 5,
            desc: 'The host\'s most repeated advice: document everything before you do anything else. Evidence degrades. Memory degrades faster.',
            items: [
              {
                name: 'The First 24 Hours',
                strength: 'Essential',
                col: 'var(--gold)',
                body: 'Write down exactly what you saw, heard, or smelled — in your own words, immediately, before you discuss it with anyone. Include time, weather, your physical state, what you had eaten, how you were feeling. Other people\'s accounts will contaminate your recollection within hours. Your unfiltered version is the most valuable thing you have.',
                source: 'Standard field methodology. Recommended by the host in every episode involving a witness account.',
              },
              {
                name: 'Photographic & Audio Record',
                strength: 'Highly Recommended',
                col: 'var(--gold)',
                body: 'Photograph tracks with a scale object (a coin, a ruler, your hand). Record ambient audio in locations of activity — many reports include sounds that witnesses did not consciously notice at the time. Do not delete anything. Storage is cheaper than regret.',
                source: 'Bigfoot Field Researchers Organization (BFRO) evidence documentation guidelines.',
              },
              {
                name: 'Establish a Baseline',
                strength: 'Recommended',
                col: 'var(--moss)',
                body: 'Before concluding that something is anomalous, document the normal. What animals pass through the area? What sounds occur at what times? What is the light like at different hours? Anomalies are only visible against a baseline. This is how both scientists and experienced field investigators work.',
                source: 'Referenced in episode discussions with Dr. Ramona (Arizona, Episode 3) and Pete the bush pilot (Alaska, Episode 2).',
              },
              {
                name: 'Geographic & Calendar Tracking',
                strength: 'Recommended',
                col: 'var(--moss)',
                body: 'Mark sightings on a map and note dates. Many entities have documented territorial patterns and seasonal cycles. The host notes that multiple episodes in this series reveal geographic clustering when sightings are mapped — a pattern that almost no individual witness is aware of.',
                source: 'Coleman, Loren. Mysterious America. Paraview Pocket Books, 2007. See also: BFRO geographic database.',
              },
            ],
          },
        ].map(({cat,rotate,desc,items})=>(
          <div key={cat} style={{marginBottom:'3rem'}}>
            {/* Category header */}
            <div style={{display:'flex',alignItems:'center',gap:'1rem',marginBottom:'1rem',paddingBottom:'.75rem',borderBottom:'1px solid var(--b)'}}>
              <Planchette size={22} color="var(--gold)" opacity={0.7} rotate={rotate}/>
              <div>
                <div className="sl" style={{marginBottom:'.1rem'}}>{cat}</div>
                <p style={{color:'var(--tm)',fontSize:'.82rem',fontStyle:'italic',fontFamily:'IM Fell English,Georgia,serif'}}>{desc}</p>
              </div>
            </div>

            {/* Items grid */}
            <div style={{display:'grid',gridTemplateColumns:'repeat(auto-fill,minmax(280px,1fr))',gap:'1px',background:'var(--b)'}}>
              {items.map(item=>(
                <div key={item.name} style={{background:'var(--bg)',padding:'1.5rem'}}>
                  <div style={{display:'flex',justifyContent:'space-between',alignItems:'flex-start',marginBottom:'.75rem',gap:'.5rem',flexWrap:'wrap'}}>
                    <div style={{fontFamily:'Cinzel,serif',fontSize:'.9rem',fontWeight:600,color:'var(--t)'}}>{item.name}</div>
                    <span style={{
                      fontFamily:'Cinzel,serif',fontSize:'.55rem',letterSpacing:'.12em',textTransform:'uppercase',
                      padding:'.15rem .5rem',border:`1px solid ${item.col}`,color:item.col,flexShrink:0,
                    }}>{item.strength}</span>
                  </div>
                  <p style={{fontSize:'.85rem',color:'var(--tm)',lineHeight:1.75,marginBottom:'.75rem'}}>{item.body}</p>
                  <div style={{display:'flex',alignItems:'flex-start',gap:'.4rem',paddingTop:'.75rem',borderTop:'1px solid var(--b)'}}>
                    <Planchette size={12} color="var(--td)" opacity={0.6} rotate={0}/>
                    <p style={{fontSize:'.72rem',color:'var(--td)',lineHeight:1.5,fontStyle:'italic'}}>{item.source}</p>
                  </div>
                </div>
              ))}
            </div>
          </div>
        ))}

        {/* Closing note */}
        <div style={{marginTop:'1rem',padding:'2rem',border:'1px solid var(--b)',background:'var(--bgc)',display:'flex',gap:'1.5rem',alignItems:'flex-start',flexWrap:'wrap'}}>
          <div style={{flexShrink:0}}>
            <Planchette size={40} color="var(--gold)" opacity={0.5} rotate={-10}/>
          </div>
          <div>
            <div className="sl" style={{marginBottom:'.5rem'}}>A Note from the Host</div>
            <p style={{fontFamily:'IM Fell English,Georgia,serif',fontStyle:'italic',fontSize:'1rem',color:'var(--t)',lineHeight:1.8,maxWidth:'680px'}}>
              "None of these protections require you to believe in the supernatural to implement them. They require only that you take seriously the possibility that you do not know everything — which, if you have been paying attention, you already do."
            </p>
          </div>
        </div>

      </div>
    </div>
  );
}

/* ============================================================
   ART PAGE
============================================================ */
function ArtPage() {
  const [filter,setFilter]=useState('All');
  const [selected,setSelected]=useState(null);
  const states=['All',...Array.from(new Set(ART_ITEMS.map(a=>a.state)))];
  const filtered=filter==='All'?ART_ITEMS:ART_ITEMS.filter(a=>a.state===filter);

  return (
    <div>
      <div className="ph">
        <div className="ctr">
          <span className="ey">Visual Archive</span>
          <h1 className="pt">Art</h1>
          <p className="ps">Original artwork created for and inspired by the podcast. One piece per legend — sometimes more.</p>
        </div>
      </div>
      <div className="ctr" style={{padding:'2.5rem 1.5rem'}}>
        <div style={{display:'flex',gap:'.4rem',flexWrap:'wrap',marginBottom:'2.5rem'}}>
          {states.map(s=><FilterBtn key={s} label={s} active={filter===s} onClick={()=>setFilter(s)}/>)}
        </div>

        <div className="gg">
          {filtered.map(item=>(
            <GalleryItem key={item.id} item={item} onClick={()=>setSelected(item)}/>
          ))}
        </div>

        <div style={{marginTop:'3rem',padding:'2rem',border:'1px dashed var(--bm)',background:'var(--bg2)',textAlign:'center'}}>
          <div className="sl" style={{marginBottom:'.75rem'}}>Add Your Artwork</div>
          <p style={{color:'var(--tm)',fontSize:'.9rem',maxWidth:'480px',margin:'0 auto 1rem'}}>Upload original artwork, fan art, or episode illustrations to populate this gallery with real images.</p>
          <button className="btn">Upload Artwork</button>
        </div>
      </div>

      {selected&&(
        <div onClick={()=>setSelected(null)} style={{position:'fixed',inset:0,background:'rgba(0,0,0,.92)',zIndex:1000,display:'flex',alignItems:'center',justifyContent:'center',padding:'2rem'}}>
          <div onClick={e=>e.stopPropagation()} style={{background:'var(--bgc)',border:'1px solid var(--b)',maxWidth:'600px',width:'100%'}}>
            <div style={{width:'100%',maxHeight:'420px',overflow:'hidden'}}>
              <ArtSVG item={selected}/>
            </div>
            <div style={{padding:'1.5rem'}}>
              <div style={{display:'flex',justifyContent:'space-between',alignItems:'flex-start',marginBottom:'.75rem'}}>
                <div>
                  <h2 style={{fontSize:'1.2rem',marginBottom:'.25rem'}}>{selected.title}</h2>
                  <div style={{fontFamily:'Cinzel,serif',fontSize:'.62rem',letterSpacing:'.12em',color:'var(--tm)',textTransform:'uppercase'}}>{selected.medium} · {selected.state} · Episode {String(selected.ep).padStart(2,'0')}</div>
                </div>
                <button onClick={()=>setSelected(null)} style={{background:'none',border:'1px solid var(--b)',color:'var(--tm)',cursor:'pointer',fontFamily:'Cinzel,serif',fontSize:'.65rem',letterSpacing:'.1em',padding:'.3rem .6rem'}}>Close</button>
              </div>
              <p style={{color:'var(--tm)',fontSize:'.85rem'}}>Artwork for <em>{selected.cryptid}</em>. Replace this placeholder by uploading the actual illustration file.</p>
            </div>
          </div>
        </div>
      )}
    </div>
  );
}

function GalleryItem({item,onClick}) {
  const [hov,setHov]=useState(false);
  return (
    <div className="gi" onClick={onClick} onMouseEnter={()=>setHov(true)} onMouseLeave={()=>setHov(false)}>
      <div style={{aspectRatio:'1',position:'relative'}}>
        <ArtSVG item={item}/>
        <div className="gio" style={{background:hov?'rgba(13,12,10,.65)':'rgba(13,12,10,0)'}}>
          <div className="gip" style={{opacity:hov?1:0}}>
            <div style={{fontFamily:'Cinzel,serif',fontSize:'.75rem',color:'var(--t)',fontWeight:600}}>{item.title}</div>
            <div style={{fontFamily:'Cinzel,serif',fontSize:'.58rem',color:'var(--gold)',letterSpacing:'.1em',textTransform:'uppercase',marginTop:'.2rem'}}>{item.medium}</div>
          </div>
        </div>
      </div>
      <div style={{padding:'.6rem .75rem',borderTop:'1px solid var(--b)'}}>
        <div style={{fontFamily:'Cinzel,serif',fontSize:'.72rem',fontWeight:600,color:'var(--t)',whiteSpace:'nowrap',overflow:'hidden',textOverflow:'ellipsis'}}>{item.title}</div>
        <div style={{fontFamily:'Cinzel,serif',fontSize:'.55rem',letterSpacing:'.1em',color:'var(--td)',textTransform:'uppercase',marginTop:'.15rem'}}>{item.state} · Ep. {String(item.ep).padStart(2,'0')}</div>
      </div>
    </div>
  );
}

/* ============================================================
   CONTACT PAGE
============================================================ */

function Planchette({size=48, color='var(--gold)', opacity=1, rotate=0}) {
  return (
    <svg width={size} height={size} viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg"
      style={{opacity, transform:`rotate(${rotate}deg)`, display:'block'}}>
      {/* Teardrop body */}
      <path d="M24 4 C14 4 7 12 7 21 C7 30 13 36 18 40 L24 44 L30 40 C35 36 41 30 41 21 C41 12 34 4 24 4Z"
        stroke={color} strokeWidth="1.2" fill="none"/>
      {/* Viewing hole */}
      <circle cx="24" cy="20" r="5" stroke={color} strokeWidth="1" fill="none"/>
      {/* Leg dots */}
      <circle cx="17" cy="38" r="1.5" fill={color}/>
      <circle cx="24" cy="43" r="1.5" fill={color}/>
      <circle cx="31" cy="38" r="1.5" fill={color}/>
      {/* Top notch */}
      <path d="M21 7 Q24 4 27 7" stroke={color} strokeWidth="0.8" fill="none"/>
      {/* Center cross-hair */}
      <line x1="24" y1="15" x2="24" y2="25" stroke={color} strokeWidth="0.5" opacity="0.5"/>
      <line x1="19" y1="20" x2="29" y2="20" stroke={color} strokeWidth="0.5" opacity="0.5"/>
    </svg>
  );
}

function OuijaBoardSVG() {
  const topLetters = 'ABCDEFGHIJKLM'.split('');
  const botLetters = 'NOPQRSTUVWXYZ'.split('');
  const numbers = '1234567890'.split('');

  // Place letters in two arcs
  function arcPos(i, total, cx, cy, rx, ry, startAngle, endAngle) {
    const t = total === 1 ? 0.5 : i / (total - 1);
    const angle = startAngle + t * (endAngle - startAngle);
    const rad = angle * Math.PI / 180;
    return { x: cx + rx * Math.cos(rad), y: cy + ry * Math.sin(rad), angle };
  }

  return (
    <svg viewBox="0 0 700 400" width="100%" xmlns="http://www.w3.org/2000/svg"
      style={{maxWidth:'700px',width:'100%',display:'block',margin:'0 auto'}}>
      {/* Board background */}
      <rect width="700" height="400" rx="18" fill="#0e2b1d" stroke="var(--gold)" strokeWidth="1.5" strokeOpacity="0.4"/>

      {/* Outer decorative border */}
      <rect x="8" y="8" width="684" height="384" rx="14" fill="none" stroke="var(--gold)" strokeWidth="0.5" strokeOpacity="0.2"/>
      <rect x="14" y="14" width="672" height="372" rx="11" fill="none" stroke="var(--gold)" strokeWidth="0.3" strokeOpacity="0.15"/>

      {/* Corner vines / flourishes */}
      {[[18,18,1,1],[682,18,-1,1],[18,382,1,-1],[682,382,-1,-1]].map(([cx,cy,sx,sy],i)=>(
        <g key={i}>
          <path d={`M${cx},${cy} Q${cx+sx*22},${cy+sy*8} ${cx+sx*38},${cy+sy*22}`} stroke="var(--gold)" strokeWidth="0.7" fill="none" strokeOpacity="0.35"/>
          <path d={`M${cx},${cy} Q${cx+sx*8},${cy+sy*22} ${cx+sx*22},${cy+sy*38}`} stroke="var(--gold)" strokeWidth="0.7" fill="none" strokeOpacity="0.35"/>
          <circle cx={cx+sx*10} cy={cy+sy*10} r="2" fill="var(--gold)" fillOpacity="0.25"/>
        </g>
      ))}

      {/* SUN (top-left) */}
      <g transform="translate(68,82)">
        <circle r="18" fill="none" stroke="var(--gold)" strokeWidth="0.8" strokeOpacity="0.5"/>
        <circle r="11" fill="var(--gold)" fillOpacity="0.12"/>
        {Array.from({length:12},(_,i)=>{
          const a=i*30*Math.PI/180;
          return <line key={i} x1={Math.cos(a)*13} y1={Math.sin(a)*13} x2={Math.cos(a)*20} y2={Math.sin(a)*20} stroke="var(--gold)" strokeWidth="0.8" strokeOpacity="0.45"/>;
        })}
        <circle r="5" fill="var(--gold)" fillOpacity="0.3"/>
        <text textAnchor="middle" y="35" fontFamily="Cinzel,serif" fontSize="7" fill="var(--gold)" fillOpacity="0.6" letterSpacing="2">SUN</text>
      </g>

      {/* MOON (top-right) */}
      <g transform="translate(632,82)">
        <path d="M0,-20 A20,20 0 1,0 14,14 A14,14 0 1,1 0,-20Z" fill="var(--gold)" fillOpacity="0.12" stroke="var(--gold)" strokeWidth="0.8" strokeOpacity="0.5"/>
        {[[-6,-8],[-10,2],[-5,12]].map(([x,y],i)=>(
          <circle key={i} cx={x} cy={y} r="1" fill="var(--gold)" fillOpacity="0.35"/>
        ))}
        <text textAnchor="middle" y="35" fontFamily="Cinzel,serif" fontSize="7" fill="var(--gold)" fillOpacity="0.6" letterSpacing="2">MOON</text>
      </g>

      {/* YES */}
      <text x="108" y="74" fontFamily="Cinzel,serif" fontSize="30" fontWeight="900"
        fill="var(--gold)" fillOpacity="0.85" letterSpacing="4">YES</text>

      {/* NO */}
      <text x="556" y="74" fontFamily="Cinzel,serif" fontSize="30" fontWeight="900"
        fill="var(--gold)" fillOpacity="0.85" letterSpacing="4">NO</text>

      {/* Title */}
      <text x="350" y="52" textAnchor="middle" fontFamily="Cinzel,serif" fontSize="13" fontWeight="600"
        fill="var(--gold)" fillOpacity="0.5" letterSpacing="6">DON'T POKE THE GHOSTS</text>

      {/* Top arc — A–M */}
      {topLetters.map((l,i)=>{
        const {x,y,angle} = arcPos(i, topLetters.length, 350, 280, 265, 185, 195, 345);
        return (
          <text key={l} x={x} y={y} textAnchor="middle" dominantBaseline="central"
            fontFamily="Cinzel,serif" fontSize="15" fontWeight="600"
            fill="var(--gold)" fillOpacity="0.75"
            transform={`rotate(${angle+90},${x},${y})`}>{l}</text>
        );
      })}

      {/* Bottom arc — N–Z */}
      {botLetters.map((l,i)=>{
        const {x,y,angle} = arcPos(i, botLetters.length, 350, 130, 265, 185, 15, 165);
        return (
          <text key={l} x={x} y={y} textAnchor="middle" dominantBaseline="central"
            fontFamily="Cinzel,serif" fontSize="15" fontWeight="600"
            fill="var(--gold)" fillOpacity="0.75"
            transform={`rotate(${angle-90},${x},${y})`}>{l}</text>
        );
      })}

      {/* Numbers row */}
      {numbers.map((n,i)=>{
        const x = 155 + i * 39;
        return (
          <text key={n} x={x} y="328" textAnchor="middle"
            fontFamily="Cinzel,serif" fontSize="14" fontWeight="600"
            fill="var(--gold)" fillOpacity="0.65">{n}</text>
        );
      })}

      {/* GOODBYE */}
      <text x="350" y="374" textAnchor="middle" fontFamily="Cinzel,serif" fontSize="16" fontWeight="600"
        fill="var(--gold)" fillOpacity="0.55" letterSpacing="8">GOODBYE</text>

      {/* Decorative center star */}
      {Array.from({length:8},(_,i)=>{
        const a=i*45*Math.PI/180;
        const r1=6, r2=14;
        return <line key={i} x1={350+Math.cos(a)*r1} y1={210+Math.sin(a)*r1} x2={350+Math.cos(a)*r2} y2={210+Math.sin(a)*r2} stroke="var(--gold)" strokeWidth="0.6" strokeOpacity="0.3"/>;
      })}
      <circle cx="350" cy="210" r="4" fill="var(--gold)" fillOpacity="0.2" stroke="var(--gold)" strokeWidth="0.5" strokeOpacity="0.4"/>

      {/* Planchette floating over board */}
      <g transform="translate(310,178)">
        {/* Planchette body */}
        <path d="M40 6 C24 6 11 18 11 31 C11 44 19 53 27 59 L40 66 L53 59 C61 53 69 44 69 31 C69 18 56 6 40 6Z"
          stroke="var(--gold)" strokeWidth="1.5" fill="rgba(18,53,36,0.85)" strokeOpacity="0.8"/>
        {/* Viewing hole */}
        <circle cx="40" cy="30" r="8" stroke="var(--gold)" strokeWidth="1.2" fill="none" strokeOpacity="0.9"/>
        {/* Crosshair */}
        <line x1="40" y1="22" x2="40" y2="38" stroke="var(--gold)" strokeWidth="0.6" strokeOpacity="0.5"/>
        <line x1="32" y1="30" x2="48" y2="30" stroke="var(--gold)" strokeWidth="0.6" strokeOpacity="0.5"/>
        {/* Leg dots */}
        <circle cx="29" cy="57" r="2.5" fill="var(--gold)" fillOpacity="0.7"/>
        <circle cx="40" cy="65" r="2.5" fill="var(--gold)" fillOpacity="0.7"/>
        <circle cx="51" cy="57" r="2.5" fill="var(--gold)" fillOpacity="0.7"/>
        {/* Top notch */}
        <path d="M35 9 Q40 5 45 9" stroke="var(--gold)" strokeWidth="1" fill="none" strokeOpacity="0.7"/>
      </g>
    </svg>
  );
}

function ContactPage() {
  const [form, setForm] = useState({name:'', subject:'', message:''});
  const [sent, setSent] = useState(false);

  function handleSubmit(e) {
    e.preventDefault();
    window.location.href = `mailto:dontpoketheghosts@gmail.com?subject=${encodeURIComponent(form.subject||'Message from the site')}&body=${encodeURIComponent(`Name: ${form.name}\n\n${form.message}`)}`;
    setSent(true);
    setTimeout(()=>setSent(false), 4000);
  }

  return (
    <div>
      {/* Page header */}
      <div className="ph">
        <div className="ctr">
          <span className="ey">Get in Touch</span>
          <h1 className="pt" style={{display:'flex',alignItems:'center',gap:'1rem',flexWrap:'wrap'}}>
            <Planchette size={52} color="var(--gold)" opacity={0.7}/>
            Contact
          </h1>
          <p className="ps">The spirits are listening. So are we.</p>
        </div>
      </div>

      <div className="ctr" style={{padding:'3rem 1.5rem'}}>

        {/* Ouija board hero */}
        <div style={{marginBottom:'3.5rem',position:'relative'}}>
          <div style={{
            border:'1px solid var(--b)',
            padding:'2rem',
            background:'var(--bgc)',
            position:'relative',
            overflow:'hidden',
          }}>
            {/* Corner planchettes */}
            <div style={{position:'absolute',top:'1rem',left:'1rem',opacity:.18}}>
              <Planchette size={36} color="var(--gold)" rotate={-30}/>
            </div>
            <div style={{position:'absolute',top:'1rem',right:'1rem',opacity:.18}}>
              <Planchette size={36} color="var(--gold)" rotate={30}/>
            </div>
            <div style={{position:'absolute',bottom:'1rem',left:'1rem',opacity:.18}}>
              <Planchette size={36} color="var(--gold)" rotate={-150}/>
            </div>
            <div style={{position:'absolute',bottom:'1rem',right:'1rem',opacity:.18}}>
              <Planchette size={36} color="var(--gold)" rotate={150}/>
            </div>
            <OuijaBoardSVG/>
          </div>
        </div>

        {/* Main content: email + form */}
        <div style={{display:'grid',gridTemplateColumns:'1fr 1fr',gap:'3rem',alignItems:'start'}} className="ab2c">

          {/* Left — direct contact */}
          <div>
            <span className="ey">Reach Out Directly</span>
            <h2 style={{fontSize:'1.4rem',marginBottom:'1.5rem'}}>The Séance Line</h2>

            {/* Email card */}
            <div style={{
              border:'1px solid var(--b)',
              background:'var(--bgc)',
              padding:'2rem',
              marginBottom:'2rem',
              position:'relative',
            }}>
              {/* Planchette icon */}
              <div style={{marginBottom:'1rem'}}>
                <Planchette size={36} color="var(--gold)" opacity={0.8}/>
              </div>
              <div className="sl" style={{marginBottom:'.4rem'}}>Email</div>
              <a href="mailto:dontpoketheghosts@gmail.com" style={{
                fontFamily:'Cinzel,serif',
                fontSize:'clamp(.8rem,2vw,1rem)',
                fontWeight:600,
                color:'var(--gold)',
                letterSpacing:'.04em',
                display:'block',
                marginBottom:'.75rem',
                wordBreak:'break-all',
              }}>
                dontpoketheghosts@gmail.com
              </a>
              <p style={{color:'var(--tm)',fontSize:'.85rem',lineHeight:1.7}}>
                For listener stories, episode tips, interview requests, and collaboration inquiries. If you've seen something you can't explain — we especially want to hear from you.
              </p>
            </div>

            {/* Response note */}
            <div style={{
              padding:'1.25rem 1.5rem',
              borderLeft:'2px solid var(--gold)',
              background:'rgba(201,168,76,0.05)',
              marginBottom:'2rem',
            }}>
              <div style={{display:'flex',alignItems:'center',gap:'.75rem',marginBottom:'.5rem'}}>
                <Planchette size={20} color="var(--gold)" opacity={0.6}/>
                <span style={{fontFamily:'Cinzel,serif',fontSize:'.65rem',letterSpacing:'.15em',textTransform:'uppercase',color:'var(--gold)'}}>Response Time</span>
              </div>
              <p style={{color:'var(--tm)',fontSize:'.85rem'}}>We read every message. The spirits are patient — responses typically arrive within a few days, though some questions require more ritual preparation than others.</p>
            </div>

            {/* What to send */}
            <div>
              <div className="sl" style={{marginBottom:'1rem'}}>Good Reasons to Write</div>
              {[
                ['You witnessed something unexplainable','We document everything.'],
                ['You have a correction or new source','We update our records.'],
                ['You want to be a guest caller','We are always casting.'],
                ['You have episode art to share','We love to see it.'],
                ['You just need to tell someone','That\'s what we\'re here for.'],
              ].map(([title,sub])=>(
                <div key={title} style={{display:'flex',alignItems:'flex-start',gap:'.75rem',padding:'.75rem 0',borderBottom:'1px solid var(--b)'}}>
                  <div style={{marginTop:'.1rem',flexShrink:0}}>
                    <Planchette size={16} color="var(--gold)" opacity={0.5}/>
                  </div>
                  <div>
                    <div style={{fontFamily:'Cinzel,serif',fontSize:'.78rem',fontWeight:600,color:'var(--t)',letterSpacing:'.03em'}}>{title}</div>
                    <div style={{fontFamily:'Lora,serif',fontStyle:'italic',fontSize:'.78rem',color:'var(--tm)',marginTop:'.1rem'}}>{sub}</div>
                  </div>
                </div>
              ))}
            </div>
          </div>

          {/* Right — contact form */}
          <div>
            <span className="ey">Send a Message</span>
            <h2 style={{fontSize:'1.4rem',marginBottom:'1.5rem'}}>Speak Into the Dark</h2>

            <form onSubmit={handleSubmit} style={{display:'flex',flexDirection:'column',gap:'1.25rem'}}>

              <div>
                <label style={{display:'flex',alignItems:'center',gap:'.5rem',fontFamily:'Cinzel,serif',fontSize:'.62rem',letterSpacing:'.2em',textTransform:'uppercase',color:'var(--gold)',marginBottom:'.5rem'}}>
                  <Planchette size={14} color="var(--gold)" opacity={0.7}/>
                  Your Name
                </label>
                <input className="inp" type="text" placeholder="What do we call you?" required
                  value={form.name} onChange={e=>setForm(f=>({...f,name:e.target.value}))}/>
              </div>

              <div>
                <label style={{display:'flex',alignItems:'center',gap:'.5rem',fontFamily:'Cinzel,serif',fontSize:'.62rem',letterSpacing:'.2em',textTransform:'uppercase',color:'var(--gold)',marginBottom:'.5rem'}}>
                  <Planchette size={14} color="var(--gold)" opacity={0.7}/>
                  Subject
                </label>
                <input className="inp" type="text" placeholder="What brings you here?" required
                  value={form.subject} onChange={e=>setForm(f=>({...f,subject:e.target.value}))}/>
              </div>

              <div>
                <label style={{display:'flex',alignItems:'center',gap:'.5rem',fontFamily:'Cinzel,serif',fontSize:'.62rem',letterSpacing:'.2em',textTransform:'uppercase',color:'var(--gold)',marginBottom:'.5rem'}}>
                  <Planchette size={14} color="var(--gold)" opacity={0.7}/>
                  Your Message
                </label>
                <textarea className="inp" placeholder="Describe what you saw, heard, or experienced. Don't leave anything out." required
                  rows={7} style={{resize:'vertical'}}
                  value={form.message} onChange={e=>setForm(f=>({...f,message:e.target.value}))}/>
              </div>

              <button type="submit" className="btn" style={{display:'flex',alignItems:'center',justifyContent:'center',gap:'.75rem',padding:'.8rem 1.5rem'}}>
                <Planchette size={18} color="currentColor" opacity={1}/>
                {sent ? 'Opening Your Mail App…' : 'Send Message'}
              </button>

              <p style={{fontSize:'.75rem',color:'var(--td)',fontStyle:'italic',textAlign:'center'}}>
                Clicking Send opens your email client with the message pre-filled.<br/>
                Or write directly to <a href="mailto:dontpoketheghosts@gmail.com" style={{color:'var(--td)'}}>dontpoketheghosts@gmail.com</a>
              </p>
            </form>
          </div>
        </div>

        {/* GOODBYE footer strip */}
        <div style={{marginTop:'4rem',position:'relative'}}>
          <div className="dv"><Planchette size={16} color="var(--gold)" opacity={0.45}/></div>
          <div style={{
            textAlign:'center',
            padding:'2.5rem 1.5rem',
            border:'1px solid var(--b)',
            background:'var(--bgc)',
            position:'relative',
            overflow:'hidden',
          }}>
            {/* Faint ouija alphabet strip */}
            <div style={{fontFamily:'Cinzel,serif',fontSize:'.65rem',letterSpacing:'.35em',color:'var(--td)',marginBottom:'1.5rem',opacity:.6}}>
              A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
            </div>

            <div style={{display:'flex',justifyContent:'center',gap:'1.5rem',marginBottom:'1.5rem',opacity:.25}}>
              <Planchette size={28} color="var(--gold)" rotate={-15}/>
              <Planchette size={28} color="var(--gold)" rotate={0}/>
              <Planchette size={28} color="var(--gold)" rotate={15}/>
            </div>

            <div style={{fontFamily:'Cinzel,serif',fontSize:'clamp(1.5rem,4vw,2.5rem)',fontWeight:900,letterSpacing:'.3em',color:'var(--gold)',opacity:.55,marginBottom:'.75rem'}}>
              GOODBYE
            </div>

            <div style={{fontFamily:'Cinzel,serif',fontSize:'.65rem',letterSpacing:'.35em',color:'var(--td)',opacity:.6}}>
              1 2 3 4 5 6 7 8 9 0
            </div>
          </div>
        </div>

      </div>
    </div>
  );
}

/* ============================================================
   APP SHELL
============================================================ */
const NAV = [{id:'home',label:'Home'},{id:'listen',label:'Listen'},{id:'videos',label:'Videos'},{id:'transcripts',label:'Transcripts'},{id:'sources',label:'Sources'},{id:'art',label:'Art'},{id:'contact',label:'Contact'}];

function App() {
  const [page,setPage] = useState('home');
  const nav = useCallback(p=>setPage(p),[]);

  const renderPage = () => {
    switch(page) {
      case 'home': return <HomePage nav={nav}/>;
      case 'videos': return <VideosPage/>;
      case 'transcripts': return <TranscriptsPage/>;
      case 'listen': return <ListenPage/>;
      case 'sources': return <SourcesPage/>;
      case 'art': return <ArtPage/>;
      case 'contact': return <ContactPage/>;
      default: return <HomePage nav={nav}/>;
    }
  };

  return (
    <>
      <nav>
        <div className="ni">
          <button className="nb" onClick={()=>setPage('home')}>Don't Poke <span>the Ghosts</span></button>
          <ul className="nl">
            {NAV.map(item=>(
              <li key={item.id}>
                <button className={page===item.id?'act':''} onClick={()=>setPage(item.id)}>{item.label}</button>
              </li>
            ))}
          </ul>
        </div>
      </nav>
      <main style={{flex:1}}>{renderPage()}</main>
      <footer>
        <div className="fi">
          <div className="fb"><strong>Don't Poke the Ghosts</strong>A 50-State Supernatural Podcast</div>
          <ul className="fl">{NAV.map(item=><li key={item.id}><button onClick={()=>setPage(item.id)}>{item.label}</button></li>)}</ul>
        </div>
      </footer>
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App/>);
</script>
</body>
</html>
