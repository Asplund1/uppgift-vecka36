uppgifter till vecka 36

uppgift 1-7

uppgift 5: 
Hittade felet: När pipelinen kördes såg jag i github-Actions att teststeget hade rött kryss. I loggen stod det tydligt vilket test som misslyckades och varför resultatet inte stämde, 1+1=3 i testet.

Fixade felet: Jag öppnade test.js och rättade testet så att det förväntade värdet matchade det riktiga resultatet, 1+1=2.

Verifierade: Efter att jag pushat ändringen kördes pipelinen om, och den blev grön vilket visade att felet var löst.