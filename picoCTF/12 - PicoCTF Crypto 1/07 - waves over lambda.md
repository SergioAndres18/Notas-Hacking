## Descripción
We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 43522`.

Hicimos muchas sustituciones para cifrar esto. ¿Puedes descifrarlo? Conéctate con `nc jupiter.challenges.picoctf.org 43522`.
## Solución
Al conectarnos a la instancia nos mostrara el siguiente texto:
```
-------------------------------------------------------------------------------
bynqelos zxex js fyhe aklq - aexthxnbf_js_b_yrxe_klpwil_yqaplhnela
-------------------------------------------------------------------------------
wxomxxn hs ozxex mls, ls j zlrx lkexlif slji sypxmzxex, ozx wyni ya ozx sxl. wxsjixs zykijnq yhe zxleos oyqxozxe ozeyhqz kynq vxejyis ya sxvlelojyn, jo zli ozx xaaxbo ya plcjnq hs oykxelno ya xlbz yozxe's flenslni xrxn bynrjbojyns. ozx klmfxeozx wxso ya yki axkkymszli, wxblhsx ya zjs plnf fxles lni plnf rjeohxs, ozx ynkf bhszjyn yn ixbc, lni mls kfjnq yn ozx ynkf ehq. ozx lbbyhnolno zli weyhqzo yho lkexlif l wyg ya iypjnyxs, lni mls oyfjnq lebzjoxbohelkkf mjoz ozx wynxs. plekym slo beyss-kxqqxi ejqzo lao, kxlnjnq lqljnso ozx pjddxn-plso. zx zli shncxn bzxxcs, l fxkkym bypvkxgjyn, l soeljqzo wlbc, ln lsbxojb lsvxbo, lni, mjoz zjs leps ieyvvxi, ozx vlkps ya zlnis yhomleis, exsxpwkxi ln jiyk. ozx ijexboye, slojsajxi ozx lnbzye zli qyyi zyki, plix zjs mlf lao lni slo iymn lpynqso hs. mx xgbzlnqxi l axm myeis kldjkf. laoxemleis ozxex mls sjkxnbx yn wylei ozx flbzo. aye sypx exlsyn ye yozxe mx iji nyo wxqjn ozlo qlpx ya iypjnyxs. mx axko pxijolojrx, lni ajo aye nyozjnq who vklbji solejnq. ozx ilf mls xnijnq jn l sxexnjof ya sojkk lni xgthjsjox wejkkjlnbx. ozx mloxe szynx vlbjajblkkf; ozx scf, mjozyho l svxbc, mls l wxnjqn jppxnsjof ya hnsoljnxi kjqzo; ozx rxef pjso yn ozx xssxg plesz mls kjcx l qlhdf lni elijlno alwejb, zhnq aeyp ozx myyixi ejsxs jnklni, lni ielvjnq ozx kym szyexs jn ijlvzlnyhs aykis. ynkf ozx qkyyp oy ozx mxso, weyyijnq yrxe ozx hvvxe exlbzxs, wxblpx pyex sypwex xrxef pjnhox, ls ja lnqxexi wf ozx lvveylbz ya ozx shn.
```

Un cifrado por sustitución es un tipo de cifrado en el que cada letra en el mensaje original se reemplaza por otra letra o símbolo. Existen herramientas online para descifrar este tipo de mensajes al descubrir qué letras o símbolos fueron sustituidos por otros.

```
-------------------------------------------------------------------------------
congrats here is your flag - frequency_is_c_over_lambda_ogfmaunraf
-------------------------------------------------------------------------------
between us there was, as i have already said somewhere, the bond of the sea. besides holding our hearts together through long periods of separation, it had the effect of making us tolerant of each other's yarnsand even convictions. the lawyerthe best of old fellowshad, because of his many years and many virtues, the only cushion on deck, and was lying on the only rug. the accountant had brought out already a box of dominoes, and was toying architecturally with the bones. marlow sat cross-legged right aft, leaning against the mizzen-mast. he had sunken cheeks, a yellow complexion, a straight back, an ascetic aspect, and, with his arms dropped, the palms of hands outwards, resembled an idol. the director, satisfied the anchor had good hold, made his way aft and sat down amongst us. we exchanged a few words lazily. afterwards there was silence on board the yacht. for some reason or other we did not begin that game of dominoes. we felt meditative, and fit for nothing but placid staring. the day was ending in a serenity of still and exquisite brilliance. the water shone pacifically; the sky, without a speck, was a benign immensity of unstained light; the very mist on the essex marsh was like a gauzy and radiant fabric, hung from the wooded rises inland, and draping the low shores in diaphanous folds. only the gloom to the west, brooding over the upper reaches, became more sombre every minute, as if angered by the approach of the sun.
```

La bandera se encuentra en la primera línea `frequency_is_c_over_lambda_ogfmaunraf`.
## Referencias
https://www.guballa.de/substitution-solver