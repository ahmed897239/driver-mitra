
                          <div>
                            <h3 className="font-extrabold text-sm sm:text-base text-slate-900 dark:text-white leading-tight">{p.businessName}</h3>
                            <p className="text-xs text-slate-500 mt-0.5">Owner: {p.ownerName} • {p.experienceYears} yrs exp.</p>
                            <div className="text-xs text-amber-500 font-extrabold mt-1">⭐ {p.rating} ({p.reviewCount} reviews)</div>
                          </div>
                        </div>
                        <p className="text-xs text-slate-600 dark:text-slate-300 line-clamp-2">{p.description}</p>
                      </div>
                      <div className="pt-2 border-t border-slate-100 dark:border-slate-800 flex items-center gap-2">
                        <a href={`tel:${p.phone}`} className="flex-1 py-2 rounded-xl bg-slate-900 hover:bg-slate-800 text-white font-bold text-xs text-center">📞 Call</a>
                        <a href={`https://wa.me/${p.whatsapp}?text=Hello%20${p.businessName},%20I%20need%20assistance.`} target="_blank" className="flex-1 py-2 rounded-xl bg-emerald-600 hover:bg-emerald-500 text-white font-bold text-xs text-center">💬 WhatsApp</a>
                        <button onClick={() => setHelpRequestProvider(p)} className="flex-1 py-2 rounded-xl bg-brand-600 hover:bg-brand-500 text-white font-bold text-xs">Request</button>
                      </div>
                    </div>
                  ))}
                </div>
              </div>
            )}
            {/* VIEW: DRIVER DASHBOARD */}
            {currentTab === 'driver-dashboard' && (
              <div className="space-y-6">
                <div className="p-6 rounded-3xl bg-slate-900 text-white flex items-center justify-between">
                  <div>
                    <h2 className="text-2xl font-black">{currentUser.name} (Driver Dashboard)</h2>
                    <p className="text-xs text-slate-400">Mobile: {currentUser.phone}</p>
                  </div>
                  <button onClick={() => navigateTo('nearby')} className="py-2 px-4 rounded-xl bg-brand-600 text-white font-bold text-xs">Find Assistance</button>
                </div>
                <div className="space-y-3">
                  <h3 className="font-extrabold text-base">Registered Commercial Fleet</h3>
                  <div className="grid grid-cols-1 sm:grid-cols-2 gap-3">
                    {vehicles.filter(v => v.userId === currentUser.id).map(v => (
                      <div key={v.id} className="p-4 rounded-2xl bg-white dark:bg-navy-850 border border-slate-200 dark:border-slate-800 shadow-sm">
                        <span className="font-black text-sm text-slate-900 dark:text-white block">{v.vehicleNumber}</span>
