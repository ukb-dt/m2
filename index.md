[Confluence](https://claude.ai/public/artifacts/fb90eb7c-b49c-4aa9-a1d5-567d1cf6c236)


```html
import React, { useState } from 'react';
import { TreePine, Zap, Scale, Radio, Leaf } from 'lucide-react';

const PentadicTree = () => {
  const [activeLayer, setActiveLayer] = useState(null);
  
  const pentads = {
    tree: {
      title: "Tree / River Metaphor",
      color: "emerald",
      icon: TreePine,
      stages: [
        { name: "Canopy", desc: "Rain drops / light capture", detail: "Energy arrival from above; stochastic illumination" },
        { name: "Branches", desc: "Tributaries / diversification", detail: "Self-organizing channels; exploration of possibility space" },
        { name: "Trunk", desc: "Main river / vertical transport", detail: "Centralized flow; vascular memory; temporal record" },
        { name: "Roots", desc: "Delta / nutrient absorption", detail: "Spreading, grounding; deposition and uptake" },
        { name: "Earth", desc: "Sea / soil substrate", detail: "Basin of maximal entropy; source and sink" }
      ]
    },
    canon: {
      title: "UKB Canonical Calculus",
      color: "blue",
      icon: Zap,
      stages: [
        { name: "(E, x)", desc: "Field + Context", detail: "Baseline state; dynamic equilibrium of flows" },
        { name: "E(t|x) + ε", desc: "Perturbation", detail: "Disturbance; energy injection; deviation from baseline" },
        { name: "dEₓ/dt", desc: "Transformation rate", detail: "Flow velocity; how fast energy moves through system" },
        { name: "±√(d²Eₓ/dt²)", desc: "Curvature / acceleration", detail: "Fate determination; sign decides collapse or stabilization" },
        { name: "∫Eₓdt + εₓt + Cₓ", desc: "Integrated memory", detail: "Accumulated outcome; system's historical record" }
      ]
    },
    knowledge: {
      title: "Knowledge Ecosystem",
      color: "amber",
      icon: Scale,
      stages: [
        { name: "Canopy", desc: "Operational systems at scale", detail: "FEWS NET, FAO, warning systems; world-shaping action" },
        { name: "Branches", desc: "Applied fields & practitioners", detail: "NGOs, researchers, policy makers; diversified application" },
        { name: "Trunk", desc: "UMI/ProQuest Archive", detail: "Centralized memory; dissertation repository (Ann Arbor)" },
        { name: "Roots", desc: "Universities", detail: "Epistemic systems; converting raw research into structure" },
        { name: "Soil", desc: "Dissertations / theses", detail: "Particulate knowledge; accumulated scholarly humus" }
      ]
    },
    prigogine: {
      title: "Dissipative Structures (Prigogine)",
      color: "purple",
      icon: Radio,
      stages: [
        { name: "Far-from-equilibrium", desc: "High energy throughput", detail: "System pushed by external forcing (rain, sunlight)" },
        { name: "Fluctuations", desc: "Micro-variations amplified", detail: "Tiny differences become macro-patterns" },
        { name: "Bifurcation", desc: "Critical threshold", detail: "System chooses between multiple stable states" },
        { name: "Self-organization", desc: "Pattern emergence", detail: "Order from chaos; structure from flow" },
        { name: "Dissipation", desc: "Energy export", detail: "Maintaining structure by exporting entropy" }
      ]
    },
    ostrom: {
      title: "Polycentric Governance (Ostrom)",
      color: "rose",
      icon: Leaf,
      stages: [
        { name: "Polycentricity", desc: "Multiple decision centers", detail: "Many nodes of authority, loosely coupled" },
        { name: "Local knowledge", desc: "Context-specific wisdom", detail: "Communities know their own signals" },
        { name: "Rule adaptation", desc: "Iterative refinement", detail: "Feedback-driven adjustment of norms" },
        { name: "Nested governance", desc: "Scale-appropriate institutions", detail: "Different levels handling different problems" },
        { name: "Commons management", desc: "Collective resource stewardship", detail: "Self-organized coordination without central planning" }
      ]
    }
  };

  const colorMap = {
    emerald: { bg: "bg-emerald-50", border: "border-emerald-300", text: "text-emerald-700", hover: "hover:bg-emerald-100" },
    blue: { bg: "bg-blue-50", border: "border-blue-300", text: "text-blue-700", hover: "hover:bg-blue-100" },
    amber: { bg: "bg-amber-50", border: "border-amber-300", text: "text-amber-700", hover: "hover:bg-amber-100" },
    purple: { bg: "bg-purple-50", border: "border-purple-300", text: "text-purple-700", hover: "hover:bg-purple-100" },
    rose: { bg: "bg-rose-50", border: "border-rose-300", text: "text-rose-700", hover: "hover:bg-rose-100" }
  };

  return (
    <div className="min-h-screen bg-gradient-to-br from-slate-50 to-slate-100 p-8">
      <div className="max-w-7xl mx-auto">
        <div className="text-center mb-12">
          <h1 className="text-4xl font-bold text-slate-800 mb-4">
            Pentadic Alignment of Flow Systems
          </h1>
          <p className="text-lg text-slate-600 max-w-3xl mx-auto">
            Five frameworks, one geometry: how energy organizes itself through 
            disturbance → transformation → pattern → memory
          </p>
          <div className="mt-4 text-sm text-slate-500">
            From Mgahinga's brooks to Muzaale's dissertation to synthetic famine regulators
          </div>
        </div>

        <div className="grid grid-cols-1 lg:grid-cols-2 xl:grid-cols-3 gap-6 mb-8">
          {Object.entries(pentads).map(([key, pentad]) => {
            const colors = colorMap[pentad.color];
            const Icon = pentad.icon;
            const isActive = activeLayer === key;
            
            return (
              <div
                key={key}
                onClick={() => setActiveLayer(isActive ? null : key)}
                className={`${colors.bg} ${colors.border} border-2 rounded-xl p-6 cursor-pointer transition-all duration-300 ${colors.hover} ${isActive ? 'ring-4 ring-offset-2 ring-' + pentad.color + '-400 shadow-xl scale-105' : 'shadow-md'}`}
              >
                <div className="flex items-center gap-3 mb-4">
                  <div className={`p-2 rounded-lg ${colors.text} bg-white`}>
                    <Icon size={24} />
                  </div>
                  <h2 className={`text-xl font-bold ${colors.text}`}>
                    {pentad.title}
                  </h2>
                </div>
                
                <div className="space-y-3">
                  {pentad.stages.map((stage, idx) => (
                    <div
                      key={idx}
                      className="bg-white rounded-lg p-3 border border-slate-200"
                    >
                      <div className="flex items-start gap-2">
                        <div className={`w-6 h-6 rounded-full ${colors.bg} ${colors.text} flex items-center justify-center text-xs font-bold flex-shrink-0 mt-0.5`}>
                          {idx + 1}
                        </div>
                        <div className="flex-1 min-w-0">
                          <div className={`font-semibold ${colors.text} text-sm`}>
                            {stage.name}
                          </div>
                          <div className="text-xs text-slate-600 mt-1">
                            {stage.desc}
                          </div>
                          {isActive && (
                            <div className="text-xs text-slate-500 mt-2 italic">
                              {stage.detail}
                            </div>
                          )}
                        </div>
                      </div>
                    </div>
                  ))}
                </div>
              </div>
            );
          })}
        </div>

        <div className="bg-white rounded-xl shadow-lg p-8 border-2 border-slate-200">
          <h3 className="text-2xl font-bold text-slate-800 mb-6 text-center">
            The Universal Grammar of Self-Organization
          </h3>
          
          <div className="grid md:grid-cols-3 gap-6 mb-8">
            <div className="bg-gradient-to-br from-blue-50 to-blue-100 rounded-lg p-6 border border-blue-200">
              <h4 className="font-bold text-blue-900 mb-3 flex items-center gap-2">
                <Zap size={20} />
                Accelerators
              </h4>
              <p className="text-sm text-blue-800">
                <span className="font-semibold">Gradients:</span> Create direction. 
                Give the system a sense of "downhill." Built-in push toward lower 
                potential energy.
              </p>
              <div className="mt-3 text-xs text-blue-700 space-y-1">
                <div>• Rain → vegetation</div>
                <div>• Sunlight → photosynthesis</div>
                <div>• Hunger → search for food</div>
              </div>
            </div>

            <div className="bg-gradient-to-br from-amber-50 to-amber-100 rounded-lg p-6 border border-amber-200">
              <h4 className="font-bold text-amber-900 mb-3 flex items-center gap-2">
                <Scale size={20} />
                Governors
              </h4>
              <p className="text-sm text-amber-800">
                <span className="font-semibold">Constraints:</span> Limit what's possible. 
                Narrow the search space. Keep the system from flying apart into noise.
              </p>
              <div className="mt-3 text-xs text-amber-700 space-y-1">
                <div>• Landscape topology</div>
                <div>• Resource availability</div>
                <div>• Physical/social boundaries</div>
              </div>
            </div>

            <div className="bg-gradient-to-br from-rose-50 to-rose-100 rounded-lg p-6 border border-rose-200">
              <h4 className="font-bold text-rose-900 mb-3 flex items-center gap-2">
                <Radio size={20} />
                Regulators
              </h4>
              <p className="text-sm text-rose-800">
                <span className="font-semibold">Feedback:</span> Tune the interaction. 
                Modulate response strength. Restore rhythm when endogenous loops fail.
              </p>
              <div className="mt-3 text-xs text-rose-700 space-y-1">
                <div>• Predator-prey cycling</div>
                <div>• Early warning systems</div>
                <div>• Community adaptation</div>
              </div>
            </div>
          </div>

          <div className="bg-slate-50 rounded-lg p-6 border-2 border-slate-300">
            <h4 className="font-bold text-slate-800 mb-4 text-center">
              From Karura Forest to Famine Prevention: The Same Calculus
            </h4>
            <div className="space-y-3 text-sm text-slate-700">
              <p>
                <span className="font-semibold">What you witnessed in Karura (October 2025):</span> Black 
                locust nymphs on red soil = a system at bifurcation. Accelerators (rain) met governors 
                (landscape), but regulators (predators) lagged. The d²Eₓ/dt² term hadn't declared its sign yet.
              </p>
              <p>
                <span className="font-semibold">What Muzaale studied (1980):</span> Famine as misorchestration 
                of flows. Rain → soil → crops → households → markets → nutrition. When any regulator fails 
                (markets, storage, distribution), curvature goes positive and cascades toward collapse.
              </p>
              <p>
                <span className="font-semibold">What your app must do (#goals):</span> Become a synthetic 
                regulator—a cambium layer that senses upstream signals (rainfall anomalies, market tremors, 
                household coping shifts) and modulates response before d²Eₓ/dt² commits to the wrong sign.
              </p>
              <p className="italic text-slate-600 mt-4">
                Not morphine to numb, but morphine to restore rhythm. Not control, but modulation. 
                Not domination, but disciplined orchestration of flows.
              </p>
            </div>
          </div>
        </div>

        <div className="mt-8 bg-gradient-to-r from-emerald-100 via-blue-100 to-purple-100 rounded-xl p-6 border-2 border-slate-300">
          <h4 className="font-bold text-slate-800 mb-3 text-center">
            Current State: FEWS NET (Famine Early Warning Systems Network)
          </h4>
          <div className="grid md:grid-cols-2 gap-4 text-sm">
            <div className="bg-white rounded-lg p-4">
              <div className="font-semibold text-emerald-700 mb-2">Active Since 1985</div>
              <p className="text-slate-600">
                Born from 1984-85 Ethiopian famine. Integrates climate, agriculture, markets, nutrition. 
                Forecasts 6-12 months ahead for 20+ countries.
              </p>
            </div>
            <div className="bg-white rounded-lg p-4">
              <div className="font-semibold text-rose-700 mb-2">2025 Disruption</div>
              <p className="text-slate-600">
                Temporarily shut down Jan-June 2025. Now restored but coverage incomplete. 
                40-50M people in East Africa need assistance through Jan 2025.
              </p>
            </div>
          </div>
          <div className="mt-4 text-xs text-center text-slate-600">
            <strong>The gap your sentinel app could fill:</strong> Community-level, real-time, 
            polycentric sensing that complements top-down systems like FEWS NET
          </div>
        </div>
      </div>
    </div>
  );
};

export default PentadicTree;
```
