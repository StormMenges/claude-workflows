# footystats-table-setup (alias: fts)

## Description
Sets up the FootyStats Football Match Filter tool with specific filters to find high-value matches for today.

## URL
https://footystats.org/matches

## Steps

1. Navigate to https://footystats.org/matches
2. 2. Click the **"Today"** tab at the top to filter for today's matches
   3. 3. Click **"Edit Filters"** in the Search Actions sidebar
      4. 4. Go to the **"Filters"** tab and apply the following settings:
         5.    - **Games Played**: 5 - 100 (default)
               -    - **Points Per Game (Home)**: 2.2 - 3
                    -    - **Points Per Game (Away)**: 0 - 1
                         -    - All other filter sliders: leave at default values
                          
                              - 5. Go to the **"Leagues"** tab and select the leagues listed below.
                                6.    **IMPORTANT**: Use the `data-value` ID to select leagues, as many league names are duplicated across countries (e.g. "Primera Division", "Super League", "FNL", etc.).
                               
                                7.      To select leagues programmatically, run this JavaScript:
                                8.     ```javascript
                                9.    const leagueIDs = [
                                10.     "16135","15688","15365","16128","15593","16590","16571",
                                11.      "15373","15467","16036","14923","14958","15377","15861",
                                12.       "16603","14937","15884","15571","16109","16719","16544",
                                13.        "16783","15056","15052","16619","16615","16789","16844",
                                14.         "16614","16699","15053","15191","15366","15639","14973",
                                15.          "16323","15055","15036","15544","15050","14930","15137",
                                16.           "14934","14935","15657","14924","15002","14904","16630",
                                17.            "16620","16737","16853","14932","14954","15361","14968",
                                18.             "14931","14977","15163","16015","15841","15985","14963",
                                19.              "15108","16735","16524","16812","16815","15283","16356",
                                20.               "15068","15632","15535","15532","15519","15248","16832",
                                21.                "16423","16863","15081","15080","15089","15177","15234",
                                22.                 "15253","16192","15111","14936","14987","15147","16817",
                                23.                  "16838","15762","15067","15071","15031","14877","15115",
                                24.                   "15717","15038","16537","16539","15015","14893","15150",
                                25.                    "15869","15040","15000","15061","15065","15523","15327",
                                26.                     "16214","15063","15033","15262","15587","15872","16627",
                                27.                      "16792","14956","15066","15047","14974","15039","16014",
                                28.                       "15671","15140","16139","14972","15199","15360","16504",
                                29.                        "16772","16540","16727","16750","16730","15243","15786",
                                30.                         "15226","15029","16604"
                                31.                        ];
                                32.                       leagueIDs.forEach(id => {
                                33.                        const a = document.querySelector(`a.filterLeague[data-value="${id}"]`);
                                34.                         if (a && !a.classList.contains('active')) a.click();
                                35.                        });
                                36.                       ```
                               
                                37.                   ### Full League List (143 leagues):
                               
                                38.               | Country | League | data-value |
                                39.           |---|---|---|
                                40.       | Africa (CAF) | CAF Champions League | 16135 |
                                41.   | Africa (CAF) | CAF Confederations Cup | 15688 |
                                42.   | Albania | Superliga | 15365 |
                                43.   | Albania | First Division | 16128 |
                                44.   | Algeria | Ligue 1 | 15593 |
                                45.   | Argentina | Copa Argentina | 16590 |
                                46.   | Argentina | Primera Division | 16571 |
                                47.   | Armenia | Armenian Premier League | 15373 |
                                48.   | Armenia | First League | 15467 |
                                49.   | Australia | A-League | 16036 |
                                50.   | Austria | Bundesliga | 14923 |
                                51.   | Austria | 2. Liga | 14958 |
                                52.   | Azerbaijan | Premyer Liqasi | 15377 |
                                53.   | Azerbaijan | First Division | 15861 |
                                54.   | Barbados | Premier Division | 16603 |
                                55.   | Belgium | Pro League | 14937 |
                                56.   | Belgium | First Division B | 15884 |
                                57.   | Belize | Belize Premier League | 15571 |
                                58.   | Benin | Championnat National | 16109 |
                                59.   | Brazil | Copa do Brasil | 16719 |
                                60.   | Brazil | Serie A | 16544 |
                                61.   | Brazil | Serie B | 16783 |
                                62.   | Bulgaria | First League | 15056 |
                                63.   | Bulgaria | Second League | 15052 |
                                64.   | Cameroon | Elite One | 16619 |
                                65.   | Chile | Primera Division | 16615 |
                                66.   | China | Chinese Super League | 16789 |
                                67.   | China | China League One | 16844 |
                                68.   | Colombia | Categoria Primera A | 16614 |
                                69.   | Colombia | Categoria Primera B | 16699 |
                                70.   | Croatia | Prva HNL | 15053 |
                                71.   | Croatia | Druga HNL | 15191 |
                                72.   | Cyprus | First Division | 15366 |
                                73.   | Cyprus | Second Division | 15639 |
                                74.   | Czech Republic | First League | 14973 |
                                75.   | Czech Republic | FNL | 16323 |
                                76.   | Denmark | Superliga | 15055 |
                                77.   | Denmark | 1st Division | 15036 |
                                78.   | Egypt | Egyptian Premier League | 15544 |
                                79.   | England | Premier League | 15050 |
                                80.   | England | Championship | 14930 |
                                81.   | England | League Cup | 15137 |
                                82.   | England | EFL League One | 14934 |
                                83.   | England | EFL League Two | 14935 |
                                84.   | England | National League | 15657 |
                                85.   | Europe | UEFA Champions League | 14924 |
                                86.   | Europe | UEFA Europa League | 15002 |
                                87.   | Europe | UEFA Europa Conference League | 14904 |
                                88.   | Faroe Islands | 1. Deild | 16630 |
                                89.   | Faroe Islands | 1. Deild Women | 16620 |
                                90.   | Finland | Finnish Cup | 16737 |
                                91.   | Finland | Womens Cup | 16853 |
                                92.   | France | Ligue 1 | 14932 |
                                93.   | France | Ligue 2 | 14954 |
                                94.   | France | National | 15361 |
                                95.   | Germany | Bundesliga | 14968 |
                                96.   | Germany | 2. Bundesliga | 14931 |
                                97.   | Germany | 3. Liga | 14977 |
                                98.   | Greece | Super League | 15163 |
                                99.   | Greece | Super League 2 | 16015 |
                                100.   | Hong Kong | Hong Kong Premier League | 15841 |
                                101.   | Hong Kong | HKFA First Division League | 15985 |
                                102.   | Hungary | NB I | 14963 |
                                103.   | Hungary | NB II | 15108 |
                                104.   | Iceland | Iceland Cup | 16735 |
                                105.   | Iceland | League Cup | 16524 |
                                106.   | India | Indian Super League | 16812 |
                                107.   | India | I-League | 16815 |
                                108.   | Indonesia | Liga 1 | 15283 |
                                109.   | Israel | Liga Leumit | 16356 |
                                110.   | Italy | Serie A | 15068 |
                                111.   | Italy | Serie B | 15632 |
                                112.   | Italy | Serie C Group A | 15535 |
                                113.   | Italy | Serie C Group B | 15532 |
                                114.   | Italy | Serie C Group C | 15519 |
                                115.   | Jordan | Jordanian Pro League | 15248 |
                                116.   | Kazakhstan | Kazakhstan Premier League | 16832 |
                                117.   | Kenya | Kenyan Premier League | 16423 |
                                118.   | Latvia | 1. Liga | 16863 |
                                119.   | Luxembourg | National Division | 15081 |
                                120.   | Luxembourg | Division of Honour | 15080 |
                                121.   | Malta | Maltese Premier League | 15089 |
                                122.   | Malta | First Division | 15177 |
                                123.   | Mexico | Liga MX | 15234 |
                                124.   | Mexico | Ascenso MX | 15253 |
                                125.   | Moldova | Moldovan National Division | 16192 |
                                126.   | Montenegro | Montenegrin First League | 15111 |
                                127.   | Netherlands | Eredivisie | 14936 |
                                128.   | Netherlands | Eerste Divisie | 14987 |
                                129.   | Netherlands | Tweede Divisie | 15147 |
                                130.   | New Caledonia | Super Ligue | 16817 |
                                131.   | New Zealand | National League | 16838 |
                                132.   | Nigeria | NPFL | 15762 |
                                133.   | Northern Ireland | NIFL Premiership | 15067 |
                                134.   | Northern Ireland | NIFL Championship | 15071 |
                                135.   | Poland | Ekstraklasa | 15031 |
                                136.   | Poland | 1. Liga | 14877 |
                                137.   | Portugal | Liga NOS | 15115 |
                                138.   | Portugal | LigaPro | 15717 |
                                139.   | Qatar | Stars League | 15038 |
                                140.   | Republic of Ireland | Premier Division | 16537 |
                                141.   | Republic of Ireland | First Division | 16539 |
                                142.   | Romania | Liga I | 15015 |
                                143.   | Russia | Russian Premier League | 14893 |
                                144.   | Russia | FNL | 15150 |
                                145.   | Saudi Arabia | Second Division | 15869 |
                                146.   | Saudi Arabia | Kings Cup | 15040 |
                                147.   | Scotland | Premiership | 15000 |
                                148.   | Scotland | Championship | 15061 |
                                149.   | Serbia | SuperLiga | 15065 |
                                150.   | Serbia | Prva Liga | 15523 |
                                151.   | Singapore | S.League | 15327 |
                                152.   | Slovakia | Super Liga | 16214 |
                                153.   | Slovenia | PrvaLiga | 15063 |
                                154.   | Slovenia | 2. SNL | 15033 |
                                155.   | Slovenia | 3. SNL | 15262 |
                                156.   | South Africa | Premier Soccer League | 15587 |
                                157.   | South Africa | National First Division | 15872 |
                                158.   | South Korea | K League 1 | 16627 |
                                159.   | South Korea | K League 2 | 16792 |
                                160.   | Spain | La Liga | 14956 |
                                161.   | Spain | Segunda Division | 15066 |
                                162.   | Switzerland | Super League | 15047 |
                                163.   | Switzerland | Challenge League | 14974 |
                                164.   | Switzerland | 1. Liga Promotion | 15039 |
                                165.   | Tahiti | Tahitian Ligue 1 | 16014 |
                                166.   | Taiwan | Taiwan Football Premier League | 15671 |
                                167.   | Thailand | Thai League T1 | 15140 |
                                168.   | Thailand | Thai League 2 | 16139 |
                                169.   | Turkey | Super Lig | 14972 |
                                170.   | Turkey | 1. Lig | 15199 |
                                171.   | UAE | Arabian Gulf League | 15360 |
                                172.   | USA | MLS | 16504 |
                                173.   | USA | US Open Cup | 16772 |
                                174.   | USA | USL Championship | 16540 |
                                175.   | USA | MLS Next Pro | 16727 |
                                176.   | Uzbekistan | Uzbekistan Super League | 16750 |
                                177.   | Uzbekistan | Super Cup | 16730 |
                                178.   | Vietnam | V.League 1 | 15243 |
                                179.   | Vietnam | V.League 2 | 15786 |
                                180.   | Wales | Welsh Premier League | 15226 |
                                181.   | Zambia | Super League | 15029 |
                                182.   | Zimbabwe | Premier Soccer League | 16604 |
                               
                                183.   6. Go to the **"Settings"** tab and confirm/set:
                                       7.    - **PPG Type**: Home vs Away PPG
                                             -    - **Sort By**: KO Time
                                                  -    - **Sorting Order**: Highest First
                                                       -    - **eSports**: Hide eSports
                                                            - 7. Click the **"SEARCH"** button to apply all filters
                                                              8. 8. The results table will show today's matches filtered by the above criteria
                                                                
                                                                 9. ## Notes
                                                                 10. - This workflow uses a free account (Limited Search, Max 25 Results)
                                                                     - - Premium filters (Corners, Cards, Odds) are not accessible on a free account
                                                                       - - League selection uses `data-value` IDs to avoid confusion with duplicate league names across countries
                                                                         - - The JavaScript snippet in step 5 can be used to select all leagues programmatically in one step
