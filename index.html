import { useState, useEffect, useRef } from "react";

const MONTHS = ["July","August","September","October","November","December","January","February","March","April","May","June"];
const STORAGE_KEY = "campaign-tracker-v9";
const MAX_CAMPAIGNS = 50;

const newEmail  = () => ({ id: Date.now()+Math.random(), image: "", notes: "", date: "" });
const newAd     = () => ({ id: Date.now()+Math.random(), image: "", notes: "", date: "" });
const newMailer = () => ({ id: Date.now()+Math.random(), image: "", notes: "", date: "" });
const defaultMonth = () => ({ emails:[newEmail()], ads:[newAd()], mailers:[newMailer()], stats:{ adSpend:"", leadTotal:"", sales:"", ecomSales:"" }, generalNotes:"" });
const defaultCampaignData = () => { const d={}; MONTHS.forEach(m=>{d[m]=defaultMonth();}); return d; };

const newCampaign = (name) => ({ id: Date.now()+Math.random(), name, color: randomColor(), data: defaultCampaignData() });

const COLORS = ["#48b4c8","#2a9d8f","#57cc99","#f4a261","#e76f51","#6366f1","#8b5cf6","#ec4899","#14b8a6","#f59e0b"];
let colorIdx = 0;
const randomColor = () => COLORS[colorIdx++ % COLORS.length];

const seed1 = () => {
  const d = defaultCampaignData();
  d["July"]     = {emails:[{id:1,image:"",date:"2024-07-01",notes:"FY2025 - July - LP - 1.99/Gal - Market Uncertainty"}],ads:[{id:2,image:"",date:"2024-07-15",notes:"Market uncertainty graphs introduced into the market."}],mailers:[{id:3,image:"",date:"2024-07-20",notes:"104 homes in Lewisberry, PA 17339 via Send Jim"}],stats:{adSpend:"3148.08",leadTotal:"117",sales:"22",ecomSales:"0"},generalNotes:""};
  d["August"]   = {emails:[{id:4,image:"",date:"2024-08-05",notes:"FY2026 - August - LP - 1.99/Gal - Market Uncertainty - Email 3"}],ads:[{id:5,image:"",date:"2024-08-10",notes:"Market uncertainty graph expanded to multiple ad sets across Facebook and Google."}],mailers:[{id:6,image:"",date:"2024-08-15",notes:"680 homes in Gettysburg Lake Heritage, PA 17325 via Send Jim"}],stats:{adSpend:"2151.95",leadTotal:"87",sales:"21",ecomSales:"0"},generalNotes:""};
  d["September"]= {emails:[{id:7,image:"",date:"",notes:"Emails Sent: 0"}],ads:[{id:8,image:"",date:"2024-09-01",notes:"Market uncertainty graph expanded."}],mailers:[{id:9,image:"",date:"2025-09-22",notes:"Prices Change Quickly: Collegeville and Harleysville"},{id:10,image:"",date:"2025-09-29",notes:"Prices Change Quickly: Lake Meade & Lake Heritage"}],stats:{adSpend:"6392.19",leadTotal:"187",sales:"39",ecomSales:"0"},generalNotes:"Did we have any sequence emails go out?"};
  d["October"]  = {emails:[{id:11,image:"",date:"2025-10-01",notes:"FY2026 - October - Email 1"},{id:12,image:"",date:"2025-10-10",notes:"FY2026 - October - Email 2"},{id:13,image:"",date:"2025-10-20",notes:"FY2026 - October - Email 3"}],ads:[{id:14,image:"",date:"2025-10-05",notes:"Fall graphics introduced into the market."}],mailers:[{id:15,image:"",date:"2025-10-06",notes:"Prices Change Quickly Collegeville & Harleysville"},{id:16,image:"",date:"2025-10-13",notes:"Winter Can Push Propane Prices Lake Meade & Lake Heritage"},{id:17,image:"",date:"2025-10-20",notes:"Winter Can Push Propane Prices Collegeville & Harleysville"},{id:18,image:"",date:"2025-10-27",notes:"Winter Can Push Propane Prices Lake Meade & Lake Heritage"}],stats:{adSpend:"7095.88",leadTotal:"229",sales:"47",ecomSales:"0"},generalNotes:""};
  d["November"] = {emails:[{id:19,image:"",date:"2025-11-01",notes:"FY2026 - November - Email 1"},{id:20,image:"",date:"2025-11-10",notes:"FY2026 - November - Email 2"},{id:21,image:"",date:"2025-11-20",notes:"FY2026 - November - Email 3"}],ads:[{id:22,image:"",date:"2025-11-05",notes:"Graphic updates: None"}],mailers:[{id:23,image:"",date:"2025-11-10",notes:"Evergreen Collegeville & Harleysville"},{id:24,image:"",date:"2025-11-24",notes:"Snowman Collegeville & Harleysville"},{id:25,image:"",date:"2025-11-10",notes:"Evergreen Lake Meade & Lake Heritage"},{id:26,image:"",date:"2025-11-24",notes:"Snowman Lake Meade & Lake Heritage"}],stats:{adSpend:"4985.88",leadTotal:"220",sales:"38",ecomSales:"0"},generalNotes:""};
  return d;
};

const initialState = () => ({
  campaigns: [{ id: "default", name: "1.99 Propane", color: "#48b4c8", data: seed1() }],
  activeCampaignId: "default",
  logo: null,
});

const C = {
  headerBg:"#e8f4f8", headerBorder:"#b8dce8", tabActive:"#2a9d8f", tabActiveTxt:"#fff", tabTxt:"#5a7a8a",
  accent1:"#2a9d8f", accent2:"#48b4c8",
  statBg:"#f0faf8", cardBg:"#ffffff", bodyBg:"#f4fbfd", border:"#d4edf4",
  labelTxt:"#7aacb8", secEmail:"#48b4c8", secAd:"#f4a261", secMailer:"#57cc99",
  sidebarBg:"#1a3a4a", sidebarBorder:"#1f4a5e",
};

const TYPE_COLORS = { Email: C.secEmail, Ad: C.secAd, Mailer: C.secMailer };
const TYPE_LABELS = { Email:"✉️", Ad:"📢", Mailer:"📬" };

// ── ImageBox ──────────────────────────────────────────────────────────────────
function ImageBox({ image, onChange, isEmail }) {
  const [input, setInput] = useState(image||"");
  const [editing, setEditing] = useState(!image);
  useEffect(()=>{ setInput(image||""); setEditing(!image); },[image]);
  const commit = () => { onChange(input.trim()); setEditing(false); };
  if (editing||!image) return (
    <div style={{background:"#f0fafb",border:`2px dashed ${C.border}`,borderRadius:8,padding:10}}>
      <div style={{fontSize:10,color:C.labelTxt,marginBottom:5,fontWeight:600}}>{isEmail?"🔗 Paste HubSpot email link":"🔗 Paste image URL"}</div>
      <div style={{display:"flex",gap:5}}>
        <input style={{flex:1,border:`1px solid ${C.border}`,borderRadius:5,padding:"4px 7px",fontSize:11,outline:"none",fontFamily:"inherit",color:"#1a4a5a"}} placeholder="https://..." value={input} onChange={e=>setInput(e.target.value)} onKeyDown={e=>{if(e.key==="Enter")commit();}} />
        <button onClick={commit} style={{fontSize:11,fontWeight:700,color:"white",background:C.accent1,border:"none",borderRadius:5,padding:"4px 10px",cursor:"pointer"}}>Add</button>
      </div>
    </div>
  );
  return (
    <div style={{background:"#f0fafb",border:`1px solid ${C.border}`,borderRadius:8,padding:10}}>
      <div style={{display:"flex",alignItems:"center",gap:7,marginBottom:7}}>
        <div style={{width:26,height:26,background:C.accent1+"18",borderRadius:5,display:"flex",alignItems:"center",justifyContent:"center",flexShrink:0}}>
          <svg width="13" height="13" fill="none" stroke={C.accent1} strokeWidth="2" viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2"/><path d="M3 9l4.5-4.5L12 9l4.5-4.5L21 9"/><path d="M3 15l4.5 4.5L12 15l4.5 4.5L21 15"/></svg>
        </div>
        <div style={{fontSize:10,color:C.labelTxt}}>{isEmail?"Email Preview":"Image linked"}</div>
      </div>
      <div style={{display:"flex",gap:5}}>
        <a href={image} target="_blank" rel="noopener noreferrer" style={{display:"flex",alignItems:"center",gap:4,fontSize:10,fontWeight:700,color:"white",background:C.accent1,borderRadius:5,padding:"4px 8px",textDecoration:"none"}}>
          <svg width="10" height="10" fill="none" stroke="currentColor" strokeWidth="2.5" viewBox="0 0 24 24"><path strokeLinecap="round" strokeLinejoin="round" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"/><path strokeLinecap="round" strokeLinejoin="round" d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z"/></svg>
          View
        </a>
        <button onClick={()=>setEditing(true)} style={{fontSize:10,color:"#555",background:"white",border:`1px solid ${C.border}`,borderRadius:5,padding:"4px 7px",cursor:"pointer"}}>Change</button>
        <button onClick={()=>{onChange("");setInput("");setEditing(true);}} style={{fontSize:10,color:"#f87171",background:"white",border:`1px solid #fca5a5`,borderRadius:5,padding:"4px 7px",cursor:"pointer"}}>✕</button>
      </div>
    </div>
  );
}

// ── ItemCard ──────────────────────────────────────────────────────────────────
function ItemCard({ item, type, idx, onUpdate, onRemove, canRemove, color }) {
  const fmtDate = d => { if(!d) return ""; const [y,mo,day]=d.split("-"); return `${mo}/${day}/${y}`; };
  return (
    <div style={{background:"#f9fdfe",border:`1px solid ${C.border}`,borderRadius:8,padding:12,marginBottom:8}}>
      <div style={{display:"flex",alignItems:"center",justifyContent:"space-between",marginBottom:8}}>
        <div style={{display:"flex",alignItems:"center",gap:8}}>
          <span style={{fontSize:10,fontWeight:700,color,textTransform:"uppercase",letterSpacing:1.2}}>{type} {idx+1}</span>
          {item.date&&<span style={{fontSize:10,color:"#fff",background:color,borderRadius:10,padding:"1px 7px",fontWeight:600}}>{fmtDate(item.date)}</span>}
        </div>
        {canRemove&&<button onClick={onRemove} style={{fontSize:10,color:"#f87171",background:"none",border:"none",cursor:"pointer"}}>✕ Remove</button>}
      </div>
      <div style={{marginBottom:8}}>
        <div style={{fontSize:10,color:C.labelTxt,marginBottom:3}}>Date</div>
        <input type="date" style={{width:"100%",border:`1px solid ${C.border}`,borderRadius:4,padding:"4px 8px",fontSize:11,outline:"none",boxSizing:"border-box",fontFamily:"inherit",color:"#1a4a5a"}} value={item.date||""} onChange={e=>onUpdate("date",e.target.value)} />
      </div>
      <ImageBox image={item.image} onChange={v=>onUpdate("image",v)} isEmail={type==="Email"} />
      <div style={{marginTop:8}}>
        <div style={{fontSize:10,color:C.labelTxt,marginBottom:3}}>Notes</div>
        <textarea style={{width:"100%",border:`1px solid ${C.border}`,borderRadius:4,padding:"4px 8px",fontSize:11,outline:"none",resize:"none",boxSizing:"border-box",fontFamily:"inherit",color:"#1a4a5a"}} rows={3} placeholder={type==="Mailer"?"Send date, audience, geography, platform...":"Notes..."} value={item.notes} onChange={e=>onUpdate("notes",e.target.value)} />
      </div>
    </div>
  );
}

// ── Section ───────────────────────────────────────────────────────────────────
function Section({ title, color, items, type, onAdd, onUpdate, onRemove }) {
  return (
    <div style={{background:C.cardBg,borderRadius:10,border:`1px solid ${C.border}`,display:"flex",flexDirection:"column"}}>
      <div style={{padding:"12px 14px 10px",borderBottom:`1px solid ${C.border}`,display:"flex",alignItems:"center",justifyContent:"space-between",flexShrink:0}}>
        <div style={{display:"flex",alignItems:"center",gap:7}}>
          <span style={{fontSize:11,fontWeight:700,letterSpacing:1.5,color,textTransform:"uppercase"}}>{title}</span>
          <span style={{fontSize:10,background:color+"22",color,borderRadius:10,padding:"1px 7px",fontWeight:700}}>{items.length}</span>
        </div>
        <button onClick={onAdd} style={{fontSize:11,color:"white",background:color,border:"none",borderRadius:5,padding:"3px 10px",cursor:"pointer",fontWeight:600}}>+ Add {type}</button>
      </div>
      <div style={{overflowY:"auto",padding:"10px 12px",maxHeight:580}}>
        {items.map((item,i)=>(
          <ItemCard key={item.id} item={item} type={type} idx={i} color={color}
            onUpdate={(f,v)=>onUpdate(i,f,v)} onRemove={()=>onRemove(i)} canRemove={items.length>1}
          />
        ))}
      </div>
    </div>
  );
}

// ── StatCard ──────────────────────────────────────────────────────────────────
function StatCard({ label, prefix, value, onChange }) {
  return (
    <div style={{background:C.statBg,borderRadius:10,padding:"12px 16px",border:`1px solid ${C.border}`}}>
      <div style={{fontSize:10,color:C.labelTxt,marginBottom:4,textTransform:"uppercase",letterSpacing:1}}>{label}</div>
      <div style={{display:"flex",alignItems:"center",gap:2}}>
        {prefix&&<span style={{color:C.labelTxt,fontSize:15}}>{prefix}</span>}
        <input style={{width:"100%",background:"transparent",border:"none",outline:"none",fontSize:20,fontWeight:700,color:"#1a4a5a",fontFamily:"inherit"}} value={value} onChange={e=>onChange(e.target.value)} placeholder="—" />
      </div>
    </div>
  );
}

// ── Timeline ──────────────────────────────────────────────────────────────────
function TimelineView({ campaignData }) {
  const [activePopup, setActivePopup] = useState(null);
  const [filterTypes, setFilterTypes] = useState({Email:true,Ad:true,Mailer:true});

  const events = [];
  MONTHS.forEach(month=>{
    const md=campaignData[month]; if(!md) return;
    [["emails","Email"],["ads","Ad"],["mailers","Mailer"]].forEach(([key,type])=>{
      md[key].forEach((item,idx)=>{
        if(!item.date) return;
        events.push({date:item.date,type,month,idx,notes:item.notes,image:item.image,id:item.id,label:`${type} ${idx+1} · ${month}`});
      });
    });
  });
  events.sort((a,b)=>a.date.localeCompare(b.date));

  const monthsWithSpend = MONTHS.map(m=>({month:m,spend:parseFloat(campaignData[m]?.stats?.adSpend||0)||0})).filter(m=>m.spend>0);
  const maxSpend = Math.max(...monthsWithSpend.map(m=>m.spend),1);
  const fmtDate = d=>{if(!d)return"";const[y,mo,day]=d.split("-");return`${mo}/${day}/${y}`;};
  const fmtMoney = v=>`$${v.toLocaleString("en-US",{minimumFractionDigits:2,maximumFractionDigits:2})}`;
  const filtered = events.filter(e=>filterTypes[e.type]);
  const monthGroups = {};
  filtered.forEach(e=>{if(!monthGroups[e.month])monthGroups[e.month]=[];monthGroups[e.month].push(e);});

  return (
    <div style={{padding:"0 0 32px"}}>
      <div style={{display:"flex",alignItems:"center",gap:10,marginBottom:24,flexWrap:"wrap"}}>
        <span style={{fontSize:11,color:C.labelTxt,fontWeight:600,textTransform:"uppercase",letterSpacing:1}}>Show:</span>
        {Object.entries(TYPE_COLORS).map(([type,color])=>(
          <button key={type} onClick={()=>setFilterTypes(prev=>({...prev,[type]:!prev[type]}))} style={{fontSize:12,fontWeight:600,padding:"5px 14px",borderRadius:20,border:`2px solid ${color}`,background:filterTypes[type]?color:"white",color:filterTypes[type]?"white":color,cursor:"pointer"}}>
            {TYPE_LABELS[type]} {type}s
          </button>
        ))}
        <span style={{marginLeft:"auto",fontSize:11,color:C.labelTxt}}>{filtered.length} events</span>
      </div>

      {monthsWithSpend.length>0&&(
        <div style={{background:C.cardBg,border:`1px solid ${C.border}`,borderRadius:10,padding:"16px 20px",marginBottom:28}}>
          <div style={{fontSize:11,fontWeight:700,letterSpacing:1.5,color:C.labelTxt,textTransform:"uppercase",marginBottom:14}}>Monthly Ad Spend</div>
          <div style={{display:"flex",alignItems:"flex-end",gap:8,height:80}}>
            {MONTHS.map(month=>{
              const spend=parseFloat(campaignData[month]?.stats?.adSpend||0)||0;
              const h=spend>0?Math.max((spend/maxSpend)*70,4):0;
              return (
                <div key={month} style={{flex:1,display:"flex",flexDirection:"column",alignItems:"center",gap:3}}>
                  <div style={{fontSize:9,color:C.accent1,fontWeight:700,height:14,display:"flex",alignItems:"flex-end"}}>{spend>0?`$${(spend/1000).toFixed(1)}k`:""}</div>
                  <div style={{width:"100%",height:h,background:spend>0?`linear-gradient(to top, ${C.accent1}, ${C.accent2})`:"transparent",borderRadius:"3px 3px 0 0"}}/>
                  <div style={{fontSize:8,color:C.tabTxt,fontWeight:600}}>{month.substring(0,3)}</div>
                </div>
              );
            })}
          </div>
        </div>
      )}

      {filtered.length===0?(
        <div style={{textAlign:"center",padding:"48px 0",color:C.labelTxt,fontSize:13}}>No events with dates yet.</div>
      ):(
        <div style={{position:"relative"}}>
          <div style={{position:"absolute",left:110,top:0,bottom:0,width:2,background:`linear-gradient(to bottom, ${C.accent2}44, ${C.accent1}44)`,borderRadius:2}}/>
          {MONTHS.map(month=>{
            const evts=monthGroups[month]; if(!evts||evts.length===0) return null;
            const spend=parseFloat(campaignData[month]?.stats?.adSpend||0)||0;
            return (
              <div key={month} style={{marginBottom:8}}>
                <div style={{display:"flex",alignItems:"center",gap:12,marginBottom:12}}>
                  <div style={{width:110,textAlign:"right",paddingRight:16}}>
                    <span style={{fontSize:12,fontWeight:800,color:"#1a4a5a"}}>{month}</span>
                    {spend>0&&<div style={{fontSize:10,color:C.accent1,fontWeight:600}}>{fmtMoney(spend)}</div>}
                  </div>
                  <div style={{width:10,height:10,borderRadius:"50%",background:C.accent1,border:"2px solid white",boxShadow:`0 0 0 2px ${C.accent1}`,zIndex:1,flexShrink:0}}/>
                  <div style={{height:1,flex:1,background:C.border}}/>
                </div>
                <div style={{paddingLeft:136,display:"flex",flexDirection:"column",gap:10,marginBottom:16}}>
                  {evts.map(evt=>{
                    const color=TYPE_COLORS[evt.type];
                    const isOpen=activePopup===evt.id;
                    return (
                      <div key={evt.id} style={{position:"relative"}}>
                        <div style={{position:"absolute",left:-26,top:14,width:26,height:2,background:color+"66"}}/>
                        <div style={{position:"absolute",left:-30,top:10,width:8,height:8,borderRadius:"50%",background:color,border:"2px solid white",boxShadow:`0 0 0 1px ${color}`,zIndex:1}}/>
                        <div onClick={()=>setActivePopup(isOpen?null:evt.id)} style={{background:"white",border:`1.5px solid ${isOpen?color:C.border}`,borderRadius:8,padding:"10px 14px",cursor:"pointer",boxShadow:isOpen?`0 4px 16px ${color}33`:"0 1px 4px rgba(0,0,0,0.04)"}}>
                          <div style={{display:"flex",alignItems:"center",gap:8}}>
                            <span style={{fontSize:11,background:color+"18",color,borderRadius:4,padding:"2px 7px",fontWeight:700}}>{TYPE_LABELS[evt.type]} {evt.type}</span>
                            <span style={{fontSize:11,color:C.labelTxt}}>{fmtDate(evt.date)}</span>
                            {evt.notes&&<span style={{fontSize:11,color:"#1a4a5a",flex:1,overflow:"hidden",textOverflow:"ellipsis",whiteSpace:"nowrap"}}>{evt.notes}</span>}
                            <span style={{fontSize:11,color:C.labelTxt,marginLeft:"auto",flexShrink:0}}>{isOpen?"▲":"▼"}</span>
                          </div>
                          {isOpen&&(
                            <div style={{marginTop:12,paddingTop:12,borderTop:`1px solid ${C.border}`}} onClick={e=>e.stopPropagation()}>
                              <div style={{display:"flex",gap:14,alignItems:"flex-start"}}>
                                {evt.image?(
                                  <a href={evt.image} target="_blank" rel="noopener noreferrer" style={{display:"flex",alignItems:"center",gap:5,fontSize:11,fontWeight:700,color:"white",background:color,borderRadius:6,padding:"7px 12px",textDecoration:"none",whiteSpace:"nowrap",flexShrink:0}}>
                                    <svg width="12" height="12" fill="none" stroke="currentColor" strokeWidth="2.5" viewBox="0 0 24 24"><path strokeLinecap="round" strokeLinejoin="round" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"/><path strokeLinecap="round" strokeLinejoin="round" d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z"/></svg>
                                    {evt.type==="Email"?"View Email":"View Image"}
                                  </a>
                                ):(
                                  <div style={{flexShrink:0,padding:"7px 12px",background:"#f0fafb",border:`1px dashed ${C.border}`,borderRadius:6,fontSize:10,color:C.labelTxt,whiteSpace:"nowrap"}}>
                                    No {evt.type==="Email"?"email":"image"} linked
                                  </div>
                                )}
                                <div style={{flex:1}}>
                                  <div style={{fontSize:11,fontWeight:700,color,marginBottom:4}}>{evt.label}</div>
                                  <div style={{fontSize:12,color:"#1a4a5a",lineHeight:1.6,whiteSpace:"pre-wrap"}}>{evt.notes||"No notes added."}</div>
                                </div>
                              </div>
                            </div>
                          )}
                        </div>
                      </div>
                    );
                  })}
                </div>
              </div>
            );
          })}
        </div>
      )}
    </div>
  );
}

// ── MAIN APP ──────────────────────────────────────────────────────────────────
export default function App() {
  const [state, setState] = useState(initialState);
  const [view, setView] = useState("tracker");
  const [activeMonth, setActiveMonth] = useState("July");
  const [savedMsg, setSavedMsg] = useState(false);
  const [showNewCampaign, setShowNewCampaign] = useState(false);
  const [newCampaignName, setNewCampaignName] = useState("");
  const [editingCampaignId, setEditingCampaignId] = useState(null);
  const [editingName, setEditingName] = useState("");
  const [confirmDelete, setConfirmDelete] = useState(null);
  const logoRef = useRef();

  useEffect(()=>{
    (async()=>{
      try {
        const r=await window.storage.get(STORAGE_KEY);
        if(r){ setState(JSON.parse(r.value)); }
      } catch {}
    })();
  },[]);

  const persist = async(s) => {
    try { await window.storage.set(STORAGE_KEY, JSON.stringify(s)); } catch {}
    setSavedMsg(true); setTimeout(()=>setSavedMsg(false),1500);
  };

  const setAndSave = (s) => { setState(s); persist(s); };

  const activeCampaign = state.campaigns.find(c=>c.id===state.activeCampaignId) || state.campaigns[0];
  const campaignData = activeCampaign?.data || defaultCampaignData();

  const updateCampaignData = (newData) => {
    const campaigns = state.campaigns.map(c=>c.id===activeCampaign.id?{...c,data:newData}:c);
    setAndSave({...state,campaigns});
  };

  const updateList = (month,section,idx,field,val) => {
    const list=[...campaignData[month][section]]; list[idx]={...list[idx],[field]:val};
    updateCampaignData({...campaignData,[month]:{...campaignData[month],[section]:list}});
  };
  const addItem = (month,section,factory) => {
    updateCampaignData({...campaignData,[month]:{...campaignData[month],[section]:[...campaignData[month][section],factory()]}});
  };
  const removeItem = (month,section,idx) => {
    updateCampaignData({...campaignData,[month]:{...campaignData[month],[section]:campaignData[month][section].filter((_,i)=>i!==idx)}});
  };
  const updateStats = (month,field,val) => {
    updateCampaignData({...campaignData,[month]:{...campaignData[month],stats:{...campaignData[month][month]?.stats,...campaignData[month].stats,[field]:val}}});
  };
  const updateNotes = (month,val) => {
    updateCampaignData({...campaignData,[month]:{...campaignData[month],generalNotes:val}});
  };
  const handleLogo = e => {
    const f=e.target.files[0]; if(!f) return;
    const r=new FileReader(); r.onload=ev=>{ setAndSave({...state,logo:ev.target.result}); }; r.readAsDataURL(f);
  };

  const addCampaign = () => {
    if(!newCampaignName.trim()) return;
    if(state.campaigns.length>=MAX_CAMPAIGNS) return;
    const c=newCampaign(newCampaignName.trim());
    const campaigns=[...state.campaigns,c];
    setAndSave({...state,campaigns,activeCampaignId:c.id});
    setNewCampaignName(""); setShowNewCampaign(false); setView("tracker"); setActiveMonth("July");
  };

  const deleteCampaign = (id) => {
    if(state.campaigns.length<=1) return;
    const campaigns=state.campaigns.filter(c=>c.id!==id);
    const activeCampaignId=id===state.activeCampaignId?campaigns[0].id:state.activeCampaignId;
    setAndSave({...state,campaigns,activeCampaignId});
    setConfirmDelete(null);
  };

  const renameCampaign = (id) => {
    if(!editingName.trim()) return;
    const campaigns=state.campaigns.map(c=>c.id===id?{...c,name:editingName.trim()}:c);
    setAndSave({...state,campaigns});
    setEditingCampaignId(null);
  };

  const m = campaignData[activeMonth];
  const fmt = v=>v?`$${parseFloat(v).toLocaleString("en-US",{minimumFractionDigits:2,maximumFractionDigits:2})}`:"—";
  const calcCPL = ()=>m.stats.adSpend&&m.stats.leadTotal?`$${(parseFloat(m.stats.adSpend)/parseFloat(m.stats.leadTotal)).toFixed(2)}`:"—";
  const calcCPS = ()=>m.stats.adSpend&&m.stats.sales?`$${(parseFloat(m.stats.adSpend)/parseFloat(m.stats.sales)).toFixed(2)}`:"—";
  const calcConv = ()=>m.stats.leadTotal&&m.stats.sales?`${((parseFloat(m.stats.sales)/parseFloat(m.stats.leadTotal))*100).toFixed(1)}%`:"—";
  const hasData = mo=>{const d=campaignData[mo];return d&&(d.stats.leadTotal||d.stats.sales||d.stats.adSpend);};

  return (
    <div style={{fontFamily:"'Inter',system-ui,sans-serif",minHeight:"100vh",background:C.bodyBg,display:"flex",flexDirection:"column"}}>

      {/* TOP HEADER */}
      <div style={{background:C.headerBg,borderBottom:`2px solid ${C.headerBorder}`,padding:"12px 20px",display:"flex",alignItems:"center",justifyContent:"space-between",flexShrink:0}}>
        <div style={{display:"flex",alignItems:"center",gap:14}}>
          <input type="file" accept="image/*" ref={logoRef} style={{display:"none"}} onChange={handleLogo} />
          {state.logo?(
            <div style={{position:"relative",cursor:"pointer"}} className="group" onClick={()=>logoRef.current.click()}>
              <img src={state.logo} alt="Logo" style={{height:40,objectFit:"contain"}} />
              <div style={{position:"absolute",inset:0,background:"rgba(255,255,255,0.75)",opacity:0,display:"flex",alignItems:"center",justifyContent:"center",borderRadius:4,fontSize:10,color:"#333",transition:"opacity .2s"}} className="group-hover:opacity-100">Change</div>
            </div>
          ):(
            <div onClick={()=>logoRef.current.click()} style={{height:40,width:90,border:`2px dashed ${C.headerBorder}`,borderRadius:6,display:"flex",alignItems:"center",justifyContent:"center",cursor:"pointer",background:"white"}}>
              <span style={{fontSize:9,color:C.accent2,textAlign:"center",lineHeight:1.4}}>Upload<br/>logo</span>
            </div>
          )}
          <div>
            <div style={{fontSize:9,letterSpacing:2,color:C.tabTxt,textTransform:"uppercase",marginBottom:1}}>Shipley Energy · Marketing</div>
            <div style={{fontSize:18,fontWeight:800,color:"#1a4a5a"}}>Campaign Tracker</div>
          </div>
        </div>
        <div style={{display:"flex",alignItems:"center",gap:10}}>
          {savedMsg&&<span style={{fontSize:11,color:C.accent1,fontWeight:600}}>✓ Saved</span>}
          <div style={{fontSize:11,color:C.tabTxt,background:"white",border:`1px solid ${C.headerBorder}`,borderRadius:6,padding:"4px 10px",fontWeight:600}}>FY2026 · Jul–Jun</div>
        </div>
      </div>

      {/* MAIN LAYOUT */}
      <div style={{display:"flex",flex:1,overflow:"hidden"}}>

        {/* SIDEBAR */}
        <div style={{width:220,background:C.sidebarBg,display:"flex",flexDirection:"column",flexShrink:0,overflowY:"auto"}}>
          <div style={{padding:"16px 12px 8px",display:"flex",alignItems:"center",justifyContent:"space-between"}}>
            <span style={{fontSize:10,fontWeight:700,letterSpacing:1.5,color:"#5a8a9a",textTransform:"uppercase"}}>Campaigns</span>
            <span style={{fontSize:10,color:"#5a8a9a"}}>{state.campaigns.length}/{MAX_CAMPAIGNS}</span>
          </div>

          {/* Campaign list */}
          <div style={{flex:1,padding:"0 8px"}}>
            {state.campaigns.map(c=>(
              <div key={c.id}>
                {editingCampaignId===c.id?(
                  <div style={{padding:"6px 8px",marginBottom:2}}>
                    <input
                      autoFocus
                      style={{width:"100%",fontSize:12,padding:"4px 6px",borderRadius:5,border:`1px solid ${C.headerBorder}`,outline:"none",boxSizing:"border-box",fontFamily:"inherit"}}
                      value={editingName}
                      onChange={e=>setEditingName(e.target.value)}
                      onKeyDown={e=>{if(e.key==="Enter")renameCampaign(c.id);if(e.key==="Escape")setEditingCampaignId(null);}}
                    />
                    <div style={{display:"flex",gap:4,marginTop:4}}>
                      <button onClick={()=>renameCampaign(c.id)} style={{flex:1,fontSize:10,background:C.accent1,color:"white",border:"none",borderRadius:4,padding:"3px 0",cursor:"pointer"}}>Save</button>
                      <button onClick={()=>setEditingCampaignId(null)} style={{flex:1,fontSize:10,background:"#2a4a5a",color:"#aaa",border:"none",borderRadius:4,padding:"3px 0",cursor:"pointer"}}>Cancel</button>
                    </div>
                  </div>
                ):(
                  <div
                    onClick={()=>{ setAndSave({...state,activeCampaignId:c.id}); setView("tracker"); setActiveMonth("July"); }}
                    style={{display:"flex",alignItems:"center",gap:8,padding:"9px 10px",borderRadius:8,marginBottom:2,cursor:"pointer",background:c.id===state.activeCampaignId?"rgba(255,255,255,0.1)":"transparent",transition:"background .15s"}}
                  >
                    <div style={{width:8,height:8,borderRadius:"50%",background:c.color,flexShrink:0}}/>
                    <span style={{fontSize:12,fontWeight:c.id===state.activeCampaignId?700:400,color:c.id===state.activeCampaignId?"white":"#8aacb8",flex:1,overflow:"hidden",textOverflow:"ellipsis",whiteSpace:"nowrap"}}>{c.name}</span>
                    {c.id===state.activeCampaignId&&(
                      <div style={{display:"flex",gap:3}} onClick={e=>e.stopPropagation()}>
                        <button onClick={()=>{setEditingCampaignId(c.id);setEditingName(c.name);}} style={{background:"none",border:"none",cursor:"pointer",color:"#5a8a9a",fontSize:11,padding:"1px 3px"}}>✏️</button>
                        {state.campaigns.length>1&&<button onClick={()=>setConfirmDelete(c.id)} style={{background:"none",border:"none",cursor:"pointer",color:"#5a8a9a",fontSize:11,padding:"1px 3px"}}>🗑</button>}
                      </div>
                    )}
                  </div>
                )}
              </div>
            ))}
            {/* + button after last campaign */}
            {state.campaigns.length<MAX_CAMPAIGNS&&!showNewCampaign&&(
              <button
                onClick={()=>setShowNewCampaign(true)}
                style={{display:"flex",alignItems:"center",gap:6,padding:"7px 10px",borderRadius:8,marginBottom:2,background:"none",border:"none",cursor:"pointer",color:"#5a8a9a",fontSize:12,width:"100%"}}
              >
                <div style={{width:18,height:18,borderRadius:"50%",border:"1.5px solid #3a6a7a",display:"flex",alignItems:"center",justifyContent:"center",flexShrink:0}}>
                  <span style={{fontSize:14,lineHeight:1,marginTop:-1}}>+</span>
                </div>
                <span>Add campaign</span>
              </button>
            )}
          </div>

          {/* Inline add campaign */}
          {showNewCampaign&&(
            <div style={{padding:"4px 8px 8px"}}>
              <div style={{background:"rgba(255,255,255,0.05)",borderRadius:8,padding:10}}>
                <input
                  autoFocus
                  style={{width:"100%",fontSize:12,padding:"5px 8px",borderRadius:5,border:`1px solid #3a6a7a`,outline:"none",boxSizing:"border-box",fontFamily:"inherit",background:"#1f4a5e",color:"white"}}
                  placeholder="Campaign name..."
                  value={newCampaignName}
                  onChange={e=>setNewCampaignName(e.target.value)}
                  onKeyDown={e=>{if(e.key==="Enter")addCampaign();if(e.key==="Escape"){setShowNewCampaign(false);setNewCampaignName("");}}}
                />
                <div style={{display:"flex",gap:5,marginTop:6}}>
                  <button onClick={addCampaign} style={{flex:1,fontSize:11,fontWeight:700,background:C.accent1,color:"white",border:"none",borderRadius:5,padding:"5px 0",cursor:"pointer"}}>Create</button>
                  <button onClick={()=>{setShowNewCampaign(false);setNewCampaignName("");}} style={{flex:1,fontSize:11,background:"#2a4a5a",color:"#aaa",border:"none",borderRadius:5,padding:"5px 0",cursor:"pointer"}}>Cancel</button>
                </div>
              </div>
            </div>
          )}
        </div>

        {/* CONTENT AREA */}
        <div style={{flex:1,display:"flex",flexDirection:"column",overflow:"hidden"}}>

          {/* Campaign header + view tabs */}
          <div style={{background:C.headerBg,borderBottom:`1px solid ${C.headerBorder}`,padding:"0 20px"}}>
            <div style={{display:"flex",alignItems:"center",gap:10,paddingTop:10,marginBottom:0}}>
              <div style={{width:10,height:10,borderRadius:"50%",background:activeCampaign?.color}}/>
              <span style={{fontSize:15,fontWeight:800,color:"#1a4a5a"}}>{activeCampaign?.name}</span>
            </div>
            <div style={{display:"flex",gap:2,marginTop:6}}>
              <button onClick={()=>setView("tracker")} style={{padding:"7px 14px",fontSize:12,fontWeight:view==="tracker"?700:500,color:view==="tracker"?C.tabActiveTxt:C.tabTxt,background:view==="tracker"?C.tabActive:"transparent",border:"none",borderRadius:"6px 6px 0 0",cursor:"pointer",whiteSpace:"nowrap"}}>
                📋 Monthly Tracker
              </button>
              <button onClick={()=>setView("timeline")} style={{padding:"7px 14px",fontSize:12,fontWeight:view==="timeline"?700:500,color:view==="timeline"?C.tabActiveTxt:C.tabTxt,background:view==="timeline"?C.tabActive:"transparent",border:"none",borderRadius:"6px 6px 0 0",cursor:"pointer",whiteSpace:"nowrap"}}>
                📅 Timeline
              </button>
              {view==="tracker"&&(
                <>
                  <div style={{width:1,background:C.headerBorder,margin:"6px 4px 0"}}/>
                  {MONTHS.map(mo=>(
                    <button key={mo} onClick={()=>setActiveMonth(mo)} style={{padding:"7px 12px",fontSize:12,fontWeight:activeMonth===mo?700:500,color:activeMonth===mo?C.tabActiveTxt:C.tabTxt,background:activeMonth===mo?C.tabActive:"transparent",border:"none",borderRadius:"6px 6px 0 0",cursor:"pointer",whiteSpace:"nowrap",position:"relative"}}>
                      {mo.substring(0,3)}
                      {hasData(mo)&&<span style={{position:"absolute",top:6,right:4,width:4,height:4,borderRadius:"50%",background:activeMonth===mo?"#a7f3d0":C.accent1}}/>}
                    </button>
                  ))}
                </>
              )}
            </div>
          </div>

          {/* Scrollable content */}
          <div style={{flex:1,overflowY:"auto",padding:"20px"}}>

            {view==="timeline"&&<TimelineView campaignData={campaignData}/>}

            {view==="tracker"&&(
              <>
                <div style={{fontSize:20,fontWeight:800,color:"#1a4a5a",marginBottom:16}}>{activeMonth}</div>
                <div style={{display:"grid",gridTemplateColumns:"repeat(4,1fr)",gap:12,marginBottom:18}}>
                  <StatCard label="Ad Spend" prefix="$" value={m.stats.adSpend} onChange={v=>updateStats(activeMonth,"adSpend",v)}/>
                  <StatCard label="Lead Total" value={m.stats.leadTotal} onChange={v=>updateStats(activeMonth,"leadTotal",v)}/>
                  <StatCard label="Sales" value={m.stats.sales} onChange={v=>updateStats(activeMonth,"sales",v)}/>
                  <StatCard label="Ecom Sales" value={m.stats.ecomSales} onChange={v=>updateStats(activeMonth,"ecomSales",v)}/>
                </div>
                <div style={{display:"grid",gridTemplateColumns:"1fr 1fr 1fr",gap:14,marginBottom:14,alignItems:"start"}}>
                  <Section title="Emails" color={C.secEmail} type="Email" items={m.emails} onAdd={()=>addItem(activeMonth,"emails",newEmail)} onUpdate={(i,f,v)=>updateList(activeMonth,"emails",i,f,v)} onRemove={i=>removeItem(activeMonth,"emails",i)}/>
                  <Section title="Ads" color={C.secAd} type="Ad" items={m.ads} onAdd={()=>addItem(activeMonth,"ads",newAd)} onUpdate={(i,f,v)=>updateList(activeMonth,"ads",i,f,v)} onRemove={i=>removeItem(activeMonth,"ads",i)}/>
                  <Section title="Mailers" color={C.secMailer} type="Mailer" items={m.mailers} onAdd={()=>addItem(activeMonth,"mailers",newMailer)} onUpdate={(i,f,v)=>updateList(activeMonth,"mailers",i,f,v)} onRemove={i=>removeItem(activeMonth,"mailers",i)}/>
                </div>
                <div style={{background:C.cardBg,borderRadius:10,padding:16,border:`1px solid ${C.border}`,marginBottom:14}}>
                  <div style={{fontSize:11,fontWeight:700,letterSpacing:1.5,color:C.labelTxt,textTransform:"uppercase",marginBottom:8}}>General Notes</div>
                  <textarea style={{width:"100%",border:`1px solid ${C.border}`,borderRadius:6,padding:"8px 12px",fontSize:13,outline:"none",resize:"none",boxSizing:"border-box",fontFamily:"inherit",color:"#1a4a5a"}} rows={4} placeholder="Any additional notes for this month..." value={m.generalNotes} onChange={e=>updateNotes(activeMonth,e.target.value)}/>
                </div>
                <div style={{background:C.cardBg,borderRadius:10,padding:16,border:`1px solid ${C.border}`,marginBottom:14,display:"flex",alignItems:"center",justifyContent:"space-between"}}>
                  <div style={{display:"flex",alignItems:"center",gap:10}}>
                    <div style={{width:34,height:34,background:"#e8f5ee",borderRadius:8,display:"flex",alignItems:"center",justifyContent:"center"}}>
                      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke={C.accent1} strokeWidth="2"><rect x="3" y="3" width="18" height="18" rx="2"/><path d="M3 9h18M3 15h18M9 3v18"/></svg>
                    </div>
                    <div>
                      <div style={{fontSize:13,fontWeight:700,color:"#1a4a5a"}}>FY2026 — Leads, Web Audience & HS Metric Tracking</div>
                      <div style={{fontSize:11,color:C.labelTxt,marginTop:1}}>Live spreadsheet · SharePoint</div>
                    </div>
                  </div>
                  <a href="https://shipleyenergy.sharepoint.com/:x:/s/Marketing/IQAVyeIaSYRpQ7yLeiT9U1OWAYWPk-G_291dpQqZS3tq408?e=hxozIu&nav=MTVfe0IyMEEyNEFBLTQzOTktNENGQS05Q0U1LTY5QjMzNUQwMjEwQn0" target="_blank" rel="noopener noreferrer" style={{display:"flex",alignItems:"center",gap:5,fontSize:12,fontWeight:700,color:"white",background:C.accent1,border:"none",borderRadius:7,padding:"8px 14px",textDecoration:"none",flexShrink:0}}>
                    <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2.5"><path strokeLinecap="round" strokeLinejoin="round" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"/></svg>
                    Open in Excel
                  </a>
                </div>
                <div style={{background:C.headerBg,border:`2px solid ${C.headerBorder}`,borderRadius:10,padding:"14px 20px",display:"flex",gap:20,alignItems:"center",flexWrap:"wrap"}}>
                  <div style={{fontSize:10,fontWeight:700,letterSpacing:1.5,color:C.tabTxt,textTransform:"uppercase"}}>{activeMonth} Summary</div>
                  {[{label:"Ad Spend",val:fmt(m.stats.adSpend)},{label:"Leads",val:m.stats.leadTotal||"—"},{label:"Sales",val:m.stats.sales||"—"},{label:"Cost / Lead",val:calcCPL()},{label:"Cost / Sale",val:calcCPS()},{label:"Lead → Sale",val:calcConv()}].map(({label,val})=>(
                    <div key={label} style={{borderLeft:`2px solid ${C.headerBorder}`,paddingLeft:14}}>
                      <div style={{fontSize:9,color:C.tabTxt,marginBottom:2,textTransform:"uppercase",letterSpacing:1}}>{label}</div>
                      <div style={{fontSize:16,fontWeight:800,color:"#2a5a6a"}}>{val}</div>
                    </div>
                  ))}
                </div>
              </>
            )}
          </div>
        </div>
      </div>

      {/* Delete confirmation */}
      {confirmDelete&&(
        <div style={{position:"fixed",inset:0,zIndex:1000,background:"rgba(0,0,0,0.5)",display:"flex",alignItems:"center",justifyContent:"center"}}>
          <div style={{background:"white",borderRadius:12,padding:24,maxWidth:340,width:"90%",boxShadow:"0 20px 60px rgba(0,0,0,0.3)"}}>
            <div style={{fontSize:16,fontWeight:700,color:"#1a4a5a",marginBottom:8}}>Delete Campaign?</div>
            <div style={{fontSize:13,color:C.labelTxt,marginBottom:20}}>This will permanently delete <strong>{state.campaigns.find(c=>c.id===confirmDelete)?.name}</strong> and all its data. This cannot be undone.</div>
            <div style={{display:"flex",gap:8}}>
              <button onClick={()=>setConfirmDelete(null)} style={{flex:1,fontSize:13,fontWeight:600,background:"#f0fafb",color:"#1a4a5a",border:`1px solid ${C.border}`,borderRadius:7,padding:"9px 0",cursor:"pointer"}}>Cancel</button>
              <button onClick={()=>deleteCampaign(confirmDelete)} style={{flex:1,fontSize:13,fontWeight:700,background:"#ef4444",color:"white",border:"none",borderRadius:7,padding:"9px 0",cursor:"pointer"}}>Delete</button>
            </div>
          </div>
        </div>
      )}
    </div>
  );
}
