# footystats-table-setup (alias: fts)

## Description
Sets up the FootyStats Football Match Filter tool with specific filters to find high-value matches for today.

## URL
https://footystats.org/matches

## Steps

1. Navigate to https://footystats.org/matches
2. Click the **"Today"** tab at the top to filter for today's matches
3. Open the filter panel by running: `document.querySelector('a.ui-toggle-filters').click()`
4. Apply ALL filters, leagues, and settings in one step by running the JavaScript below, then click SEARCH.

```javascript
// === FILTERS ===
// Games Played: leave at default (5-60 max range)
// PPG Home: 2.2 - 3
document.getElementById('sliderpre_match_home_ppg').noUiSlider.set([2.2, 3]);
// PPG Away: 0 - 1
document.getElementById('sliderpre_match_away_ppg').noUiSlider.set([0, 1]);

// === SETTINGS ===
// Navigate to Settings tab and apply (these use select elements with class 'update_sorting_options')
const selects = document.querySelectorAll('select.update_sorting_options');
selects.forEach(s => {
  if ([...s.options].some(o => o.value === 'home_away')) s.value = 'home_away';
  if ([...s.options].some(o => o.value === 'date_unix') && s.classList.contains('active_sorting_options')) s.value = 'date_unix';
  if ([...s.options].some(o => o.value === 'DESC') && [...s.options].some(o => o.value === 'ASC')) s.value = 'DESC';
  if ([...s.options].some(o => o.text === 'Hide eSports')) s.value = '0';
  s.dispatchEvent(new Event('change'));
});

// === LEAGUES (152 leagues) ===
const leagueIDs = [
  "16135","15688","15365","16128","15593","16590","16571",
  "15373","15467","16036","14923","14958","15377","15861",
  "16603","14937","15884","15571","16109","16719","16544",
  "16783","15056","15052","16619","16615","16789","16844",
  "16614","16699","15053","15191","15366","15639","14973",
  "16323","15055","15036","15544","15050","14930","15137",
  "14934","14935","15657","14924","15002","14904","16630",
  "16620","16737","16853","14932","14954","15361","14968",
  "14931","14977","15163","16015","15841","15985","14963",
  "15108","16735","16524","16812","16815","15283","16356",
  "15068","15632","15535","15532","15519","15248","16832",
  "16423","16863","15081","15080","15089","15177","15234",
  "15253","16192","15111","14936","14987","15147","16817",
  "16838","15762","15067","15071","15031","14877","15115",
  "15717","15038","16537","16539","15015","14893","15150",
  "15869","15040","15000","15061","15065","15523","15327",
  "16214","15063","15033","15262","15587","15872","16627",
  "16792","14956","15066","15047","14974","15039","16014",
  "15671","15140","16139","14972","15199","15360","16504",
  "16772","16540","16727","16750","16730","15243","15786",
  "15226","15029","16604",
  "16363","16558","15741","15783","14943","16576","16575",
  "16213","15091"
];
leagueIDs.forEach(id => {
  const a = document.querySelector(`a.filterLeague[data-value="${id}"]`);
  if (a && !a.classList.contains('active')) a.click();
});
```

5. Click the **"SEARCH"** button to apply all filters

The results table will show today's matches filtered by the above criteria.

### Full League List (152 leagues):

| Country | League | data-value |
|---|---|---|
| Africa (CAF) | CAF Champions League | 16135 |
| Africa (CAF) | CAF Confederations Cup | 15688 |
| Albania | Superliga | 15365 |
| Albania | First Division | 16128 |
| Algeria | Ligue 1 | 15593 |
| Argentina | Copa Argentina | 16590 |
| Argentina | Primera Division | 16571 |
| Armenia | Armenian Premier League | 15373 |
| Armenia | First League | 15467 |
| Australia | A-League | 16036 |
| Austria | Bundesliga | 14923 |
| Austria | 2. Liga | 14958 |
| Azerbaijan | Premyer Liqasi | 15377 |
| Azerbaijan | First Division | 15861 |
| Barbados | Premier Division | 16603 |
| Belgium | Pro League | 14937 |
| Belgium | First Division B | 15884 |
| Belize | Belize Premier League | 15571 |
| Benin | Championnat National | 16109 |
| Brazil | Copa do Brasil | 16719 |
| Brazil | Serie A | 16544 |
| Brazil | Serie B | 16783 |
| Bulgaria | First League | 15056 |
| Bulgaria | Second League | 15052 |
| Cameroon | Elite One | 16619 |
| Chile | Primera Division | 16615 |
| China | Chinese Super League | 16789 |
| China | China League One | 16844 |
| Colombia | Categoria Primera A | 16614 |
| Colombia | Categoria Primera B | 16699 |
| Croatia | Prva HNL | 15053 |
| Croatia | Druga HNL | 15191 |
| Cyprus | First Division | 15366 |
| Cyprus | Second Division | 15639 |
| Czech Republic | First League | 14973 |
| Czech Republic | FNL | 16323 |
| Denmark | Superliga | 15055 |
| Denmark | 1st Division | 15036 |
| Egypt | Egyptian Premier League | 15544 |
| England | Premier League | 15050 |
| England | Championship | 14930 |
| England | League Cup | 15137 |
| England | EFL League One | 14934 |
| England | EFL League Two | 14935 |
| England | National League | 15657 |
| England | League One | 14943 |
| Europe | UEFA Champions League | 14924 |
| Europe | UEFA Europa League | 15002 |
| Europe | UEFA Europa Conference League | 14904 |
| Faroe Islands | 1. Deild | 16630 |
| Faroe Islands | 1. Deild Women | 16620 |
| Finland | Finnish Cup | 16737 |
| Finland | Womens Cup | 16853 |
| France | Ligue 1 | 14932 |
| France | Ligue 2 | 14954 |
| France | National | 15361 |
| Germany | Bundesliga | 14968 |
| Germany | 2. Bundesliga | 14931 |
| Germany | 3. Liga | 14977 |
| Greece | Super League | 15163 |
| Greece | Super League 2 | 16015 |
| Hong Kong | Hong Kong Premier League | 15841 |
| Hong Kong | HKFA First Division League | 15985 |
| Hungary | NB I | 14963 |
| Hungary | NB II | 15108 |
| Iceland | Iceland Cup | 16735 |
| Iceland | League Cup | 16524 |
| India | Indian Super League | 16812 |
| India | I-League | 16815 |
| Indonesia | Liga 1 | 15283 |
| Israel | Israeli Premier League | 16363 |
| Israel | Liga Leumit | 16356 |
| Italy | Serie A | 15068 |
| Italy | Serie B | 15632 |
| Italy | Serie C Group A | 15535 |
| Italy | Serie C Group B | 15532 |
| Italy | Serie C Group C | 15519 |
| Jordan | Jordanian Pro League | 15248 |
| Kazakhstan | Kazakhstan Premier League | 16832 |
| Kenya | Kenyan Premier League | 16423 |
| Latvia | 1. Liga | 16863 |
| Luxembourg | National Division | 15081 |
| Luxembourg | Division of Honour | 15080 |
| Malta | Maltese Premier League | 15089 |
| Malta | First Division | 15177 |
| Mexico | Liga MX | 15234 |
| Mexico | Ascenso MX | 15253 |
| Moldova | Moldovan National Division | 16192 |
| Montenegro | Montenegrin First League | 15111 |
| Netherlands | Eredivisie | 14936 |
| Netherlands | Eerste Divisie | 14987 |
| Netherlands | Tweede Divisie | 15147 |
| New Caledonia | Super Ligue | 16817 |
| New Zealand | National League | 16838 |
| Nigeria | NPFL | 15762 |
| Northern Ireland | NIFL Premiership | 15067 |
| Northern Ireland | NIFL Championship | 15071 |
| Norway | Eliteserien | 16558 |
| Poland | Ekstraklasa | 15031 |
| Poland | 1. Liga | 14877 |
| Portugal | Liga NOS | 15115 |
| Portugal | LigaPro | 15717 |
| Qatar | Stars League | 15038 |
| Republic of Ireland | Premier Division | 16537 |
| Republic of Ireland | First Division | 16539 |
| Romania | Liga I | 15015 |
| Russia | Russian Premier League | 14893 |
| Russia | FNL | 15150 |
| Saudi Arabia | Professional League | 15741 |
| Saudi Arabia | First Division | 15783 |
| Saudi Arabia | Second Division | 15869 |
| Saudi Arabia | Kings Cup | 15040 |
| Scotland | Premiership | 15000 |
| Scotland | Championship | 15061 |
| Serbia | SuperLiga | 15065 |
| Serbia | Prva Liga | 15523 |
| Singapore | S.League | 15327 |
| Slovakia | Super Liga | 16214 |
| Slovenia | PrvaLiga | 15063 |
| Slovenia | 2. SNL | 15033 |
| Slovenia | 3. SNL | 15262 |
| South Africa | Premier Soccer League | 15587 |
| South Africa | National First Division | 15872 |
| South Korea | K League 1 | 16627 |
| South Korea | K League 2 | 16792 |
| Spain | La Liga | 14956 |
| Spain | Segunda Division | 15066 |
| Sweden | Allsvenskan | 16576 |
| Sweden | Superettan | 16575 |
| Switzerland | Super League | 15047 |
| Switzerland | Challenge League | 14974 |
| Switzerland | 1. Liga Promotion | 15039 |
| Tahiti | Tahitian Ligue 1 | 16014 |
| Taiwan | Taiwan Football Premier League | 15671 |
| Thailand | Thai League T1 | 15140 |
| Thailand | Thai League 2 | 16139 |
| Turkey | Super Lig | 14972 |
| Turkey | 1. Lig | 15199 |
| UAE | Arabian Gulf League | 15360 |
| Ukraine | Ukrainian Premier League | 16213 |
| Ukraine | Persha Liga | 15091 |
| USA | MLS | 16504 |
| USA | US Open Cup | 16772 |
| USA | USL Championship | 16540 |
| USA | MLS Next Pro | 16727 |
| Uzbekistan | Uzbekistan Super League | 16750 |
| Uzbekistan | Super Cup | 16730 |
| Vietnam | V.League 1 | 15243 |
| Vietnam | V.League 2 | 15786 |
| Wales | Welsh Premier League | 15226 |
| Zambia | Super League | 15029 |
| Zimbabwe | Premier Soccer League | 16604 |

## Notes
- This workflow uses a free account (Limited Search, Max 25 Results)
- Premium filters (Corners, Cards, Odds) are not accessible on a free account
- League selection uses data-value IDs to avoid confusion with duplicate league names across countries
- The JavaScript in step 4 handles filters, settings, AND league selection all at once for speed
- The filter panel must be opened (step 3) before running the JavaScript
- Games Played slider max is 60 on the site, so 5-60 is the effective full range
