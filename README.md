"# replication_climate_IAM" 


Der vorliegende Code ist eine Replikationsstudie zu dem Papier ["Optimal Climate Policy As If Transition Matters" von Emanuele Campiglio, Simon Dietz, Frank Venmans (2024)](https://www.cesifo.org/en/publications/2022/working-paper/optimal-climate-policy-if-transition matters#:~:text=The%20optimal%20transition%20to%20a,and%20economic%20and%20climatic%20shocks.)


# Verbale Zusammenfassung des Modells
Die verbale Zusammenfassung sowie mathematische Erläuterungen der Modellstruktur befinden sich in der PDF. Diese ist jedoch noch ein Working Paper (auch die Rechtschreibung und Grammatik sowie Formalia) und nicht vollständig, da ich bisher hauptsächlich mit dem Code beschäftigt war. Die bestehenden Erklärungen sollten jedoch einen ersten Eindruck über die Modellstruktur vermitteln. 

# Ziel und Struktur 
In der Replikation der Studie ist es mein Ziel, die optimale Rate des Desinvestments zu berechnen, sowie die dadurch entstehenden Kosten (Verluste von Ressourcen durch Abriss und Stilllegung - "stranded assets") zu schätzen. Dafür vereinfache ich das originale Modell, ähnlich dem "straw man model" aus dem angegebenen Papier. Ich löse das vereinfachte Modell in Python unter Anwendung der odeint-Funktion aus dem SciPy Paket. Diese Funktion wendet den LSODA (Livermore Solver for Irdniary Differential Equations with Automatic method switching for stiff and nonstiff problems) Algorithmus an. Dieser Algorithmus wählt automatisch zwischen der Adams-Bashforth Methode und Backward Differentiation Verfahren, je nach Beschaffenheit des Differentialgleichungssystems. Dies geschieht im File "optimal_varphi", wobei die Variable Varphi die (Des-)investmentrate aus fossilen in grüne Kapitalien darstellt. Das System optimiert den gesamtgesellschaftlichen Output über die Variation von Varphi (Kontrollvariable), unter der Nebenbedingung dass die im System entstehenden Emissionen (Emissionen entstehen durch den Bestand an fossilen Kapitalien) die Temperatur unter 1,5 Grad Celsius halten. 

Der derzeitige Stand der Replikation ist, dass es noch in Arbeit ist. Die Skalierung des Plots der Stranded Assets ist noch nicht korrekt, allerdings gibt Python eine sinnvolle (d.h. näherungsweise dem originalen Papier entsprechende) Schätzung für die entstehenden Kosten (stranded assets) sowie die jährlich optimale Desinvestment-Rate aus. 

