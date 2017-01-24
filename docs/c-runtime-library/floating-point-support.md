---
title: "Prise en charge de la virgule flottante | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.math"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "chiffres à virgule flottante"
  - "chiffres à virgule flottante, routines mathématiques"
  - "routines mathématiques"
ms.assetid: e4fcaf69-5c8e-4854-a9bb-1f412042131e
caps.latest.revision: 17
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Prise en charge de la virgule flottante
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

De nombreuses fonctions de la bibliothèque Runtime de Microsoft requièrent la prise en charge de la virgule flottante par un coprocesseur mathématique ou par des bibliothèques de virgules flottantes qui accompagnent le compilateur.  Les fonctions prenant en charge les virgules flottantes sont chargées uniquement si nécessaire.  
  
 Quand vous utilisez un spécificateur de type virgule flottante dans la chaîne de format d'un appel à une fonction dans la famille `printf` ou `scanf`, vous devez spécifier une valeur à virgule flottante ou un pointeur vers une valeur à virgule flottante dans la liste d'arguments pour indiquer au compilateur que la prise en charge de la virgule flottante est requise.  
  
 Pour obtenir un exemple de code qui montre comment gérer les exceptions de virgule flottante, voir [\_fpieee\_flt](../c-runtime-library/reference/fpieee-flt.md).  
  
 La précision virgule flottante des valeurs intermédiaires est contrôlée par les fonctions [\_control87, \_controlfp, \_\_control87\_2](../c-runtime-library/reference/control87-controlfp-control87-2.md).  Par défaut, le contrôle de précision dans `_controlfp` a la valeur 53 bits \(\_PC\_53\).  Une liaison à l'aide de FP10.OBJ remplace le contrôle de précision par défaut par 64 bits \(\_PC\_64\).  Sur la ligne de commande de l'éditeur de liens, FP10.OBJ doit apparaître avant LIBC.LIB, LIBCMT.LIB ou MSVCRT.LIB.  
  
### Fonctions à virgule flottante  
  
|Routine|Utilisation|Équivalent .NET Framework|  
|-------------|-----------------|-------------------------------|  
|[abs](../Topic/abs.md)|Retourner la valeur absolue de `int`|[\<caps:sentence id\="tgt14" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[acos, acosf](../c-runtime-library/reference/acos-acosf-acosl.md)|Calculer l'arc cosinus|[\<caps:sentence id\="tgt17" sentenceid\="954a441495360a1fa8b0170297b2ff38" class\="tgtSentence"\>System::Math::Acos\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.acos.aspx)|  
|[asin, asinf](../c-runtime-library/reference/asin-asinf-asinl.md)|Calculer l'arc sinus|[\<caps:sentence id\="tgt20" sentenceid\="313917cde9698a0924536719f5bece25" class\="tgtSentence"\>System::Math::Asin\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.asin.aspx)|  
|[atan, atanf, atan2, atan2f](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Calculer l'arc tangente|[System::Math::Atan](https://msdn.microsoft.com/en-us/library/system.math.atan.aspx), [System::Math::Atan2](https://msdn.microsoft.com/en-us/library/system.math.atan2.aspx)|  
|[atof, \_atof\_l, \_wtof, \_wtof\_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Convertir une chaîne de caractères en valeur à virgule flottante double précision|[System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tosingle.aspx), [System::Convert::ToDouble](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)|  
|[Fonctions de Bessel](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|Calculer les fonctions de Bessel `_j0`, `_j1`, `_jn`, `_y0`, `_y1`, `_yn`|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_cabs](../c-runtime-library/reference/cabs.md)|Trouver la valeur absolue du nombre complexe|Non applicable.|  
|[cbrt](../c-runtime-library/reference/cbrt-cbrtf-cbrtl.md)|Calculer la racine cubique|Non applicable.|  
|[ceil, ceilf](../c-runtime-library/reference/ceil-ceilf-ceill.md)|Trouver la valeur plafond de l'entier|[\<caps:sentence id\="tgt39" sentenceid\="656009d71fb974368bded363746de018" class\="tgtSentence"\>System::Math::Ceiling\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.ceiling.aspx)|  
|[\_chgsign, \_chgsignf, \_chgsignl](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|Inverser le signe de l'argument à virgule flottante double précision ou à virgule flottante double précision long|Non applicable.|  
|[\_clear87, \_clearfp](../c-runtime-library/reference/clear87-clearfp.md)|Obtenir et effacer le mot d'état à virgule flottante|Non applicable.|  
|[\_control87, \_controlfp, \_\_control87\_2](../c-runtime-library/reference/control87-controlfp-control87-2.md), [\_controlfp\_s](../c-runtime-library/reference/controlfp-s.md)|Obtenir l'ancien mot de contrôle à virgule flottante et définir la nouvelle valeur du mot de contrôle|Non applicable.|  
|[copysign, copysignf, copysignl, \_copysign, \_copysignf, \_copysignl](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|Retourner une valeur avec le signe d'une autre|Non applicable.|  
|[cos, cosf, cosh, coshf](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|Calculer le cosinus|[System::Math::Cos](https://msdn.microsoft.com/en-us/library/system.math.cos.aspx), [System::Math::Cosh](https://msdn.microsoft.com/en-us/library/system.math.cosh.aspx)|  
|[difftime](../c-runtime-library/reference/difftime-difftime32-difftime64.md)|Calculer la différence entre deux valeurs d'heure spécifiées|[\<caps:sentence id\="tgt54" sentenceid\="5f4f365a3cd7f368db2f6ce31b797fdf" class\="tgtSentence"\>System::DateTime::Subtract\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.datetime.subtract.aspx)|  
|[div](../c-runtime-library/reference/div.md)|Diviser un entier par un autre, en retournant le quotient et le reste|Non applicable.|  
|[\_ecvt](../c-runtime-library/reference/ecvt.md), [\_ecvt\_s](../c-runtime-library/reference/ecvt-s.md)|Convertir `double` en chaine de caractères de longueur spécifiée|[\<caps:sentence id\="tgt60" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[exp, expf](../c-runtime-library/reference/exp-expf.md)|Calculer la fonction exponentielle|[\<caps:sentence id\="tgt63" sentenceid\="81a65df6ac66cdc4a4b12c2f7e555487" class\="tgtSentence"\>System::Math::Exp\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.exp.aspx)|  
|[fabs, fabsf](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|Trouver la valeur absolue|[\<caps:sentence id\="tgt66" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[\_fcvt](../c-runtime-library/reference/fcvt.md), [\_fcvt\_s](../c-runtime-library/reference/fcvt-s.md)|Convertir `double` en chaîne avec le nombre spécifié de chiffres après la virgule décimale|[\<caps:sentence id\="tgt69" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[\_finite](../c-runtime-library/reference/finite-finitef.md)|Déterminer si la valeur à virgule flottante double précision donnée est finie|[\<caps:sentence id\="tgt72" sentenceid\="8d081c50adeda3dde4cebab81a0b3583" class\="tgtSentence"\>System::Double::IsInfinity\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double.isinfinity.aspx)|  
|[floor, floorf](../c-runtime-library/reference/floor-floorf-floorl.md)|Trouver le plus grand entier inférieur ou égal à l'argument|[\<caps:sentence id\="tgt75" sentenceid\="609db9ab0433b647d5350d3b965d70f9" class\="tgtSentence"\>System::Math::Floor\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.floor.aspx)|  
|[fmod, fmodf](../c-runtime-library/reference/fmod-fmodf.md)|Trouver le reste à virgule flottante|[\<caps:sentence id\="tgt78" sentenceid\="127a04426267ccb17fb4b566ad56de9c" class\="tgtSentence"\>System::Math::IEEERemainder\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.ieeeremainder.aspx)|  
|[\_fpclass](../c-runtime-library/reference/fpclass-fpclassf.md)|Retourner le mot d'état contenant des informations sur la classe à virgule flottante|[System::Double::IsInfinity](https://msdn.microsoft.com/en-us/library/system.double.isinfinity.aspx), [System::Double::IsNegativeInfinity](https://msdn.microsoft.com/en-us/library/system.double.isnegativeinfinity.aspx), [System::Double::IsPositiveInfinity](https://msdn.microsoft.com/en-us/library/system.double.ispositiveinfinity.aspx), [System::Double::IsNan](https://msdn.microsoft.com/en-us/library/system.double.isnan.aspx)|  
|[\_fpieee\_flt](../c-runtime-library/reference/fpieee-flt.md)|Appeler un gestionnaire d'interruptions défini par l'utilisateur pour les exceptions à virgule flottante IEEE|Non applicable.|  
|[\_fpreset](../c-runtime-library/reference/fpreset.md)|Réinitialiser le package mathématique à virgule flottante||  
|[frexp](../c-runtime-library/reference/frexp.md)|Calculer la valeur exponentielle|Non applicable.|  
|[\_gcvt](../c-runtime-library/reference/gcvt.md), [\_gcvt\_s](../c-runtime-library/reference/gcvt-s.md)|Convertir une valeur à virgule flottante en chaîne de caractères|[\<caps:sentence id\="tgt92" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[hypot, hypotf, hypotl, \_hypot, \_hypotf, \_hypotl](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|Calculer l'hypoténuse du triangle rectangle|Non applicable.|  
|[\_isnan](../c-runtime-library/reference/isnan-isnan-isnanf.md)|Rechercher une valeur non numérique \(NaN\) dans la valeur à virgule flottante double précision donnée|[\<caps:sentence id\="tgt97" sentenceid\="18f7dc07d0c506c23f2f7eb89262d274" class\="tgtSentence"\>System::Double::IsNan\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double.isnan.aspx)|  
|[labs](../misc/labs-llabs.md)|Retourner la valeur absolue de `long`|[\<caps:sentence id\="tgt100" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[ldexp](../c-runtime-library/reference/ldexp.md)|Calculer le produit de l'argument et de 2<sup>exp</sup> \(puissance spécifiée\)|[\<caps:sentence id\="tgt103" sentenceid\="839e85fe5fb98e8520d40a703d06932b" class\="tgtSentence"\>System::Math::Pow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)|  
|[ldiv](../c-runtime-library/reference/ldiv-lldiv.md)|Diviser un entier `long` par un autre, en retournant le quotient et le reste|Non applicable.|  
|[log, logf, log10, log10f](../c-runtime-library/reference/log-logf-log10-log10f.md)|Calculer le logarithme naturel ou en base 10|[System::Math::Log](https://msdn.microsoft.com/en-us/library/system.math.log.aspx), [System::Math::Log10](https://msdn.microsoft.com/en-us/library/system.math.log10.aspx)|  
|[\_logb](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|Extraire la valeur exponentielle de l'argument à virgule flottante double précision|Non applicable.|  
|[\_lrotl, \_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|Décaler `unsigned long int` vers la gauche \(`_lrotl`\) ou la droite \(`_lrotr`\)|Non applicable.|  
|[\_matherr](../c-runtime-library/reference/matherr.md)|Gérer les erreurs mathématiques|Non applicable.|  
|[\_\_max](../c-runtime-library/reference/max.md)|Retourner la plus grande de deux valeurs|[\<caps:sentence id\="tgt121" sentenceid\="6f9dcb228534c3e5b0013615b2b1d003" class\="tgtSentence"\>System::Math::Max\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.max.aspx)|  
|[\_\_min](../c-runtime-library/reference/min.md)|Retourner la plus petite de deux valeurs|[\<caps:sentence id\="tgt124" sentenceid\="ff471983fc666dec7ba58b17a0bf76e6" class\="tgtSentence"\>System::Math::Min\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.min.aspx)|  
|[modf, modff](../c-runtime-library/reference/modf-modff-modfl.md)|Diviser l'argument en un entier et une partie fractionnaire|Non applicable.|  
|[nan, nanf, nanl](../c-runtime-library/reference/nan-nanf-nanl.md)|Retourner une valeur NaN silencieuse|[\<caps:sentence id\="tgt129" sentenceid\="c251043405ffa73fe857c83428b58fdc" class\="tgtSentence"\>System::Double::NaN\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double.nan.aspx)|  
|[\_nextafter](../c-runtime-library/reference/nextafter-functions.md)|Retourner le prochain voisin représentable|Non applicable.|  
|[pow, powf](../c-runtime-library/reference/pow-powf-powl.md)|Calculer la valeur élevée à une puissance|[\<caps:sentence id\="tgt135" sentenceid\="839e85fe5fb98e8520d40a703d06932b" class\="tgtSentence"\>System::Math::Pow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)|  
|[printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|Écrire les données dans `stdout` selon le format spécifié|[System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx), [System::Console::WriteLine](https://msdn.microsoft.com/en-us/library/system.console.writeline.aspx)|  
|[rand](../c-runtime-library/reference/rand.md), [rand\_s](../c-runtime-library/reference/rand-s.md)|Obtenir un nombre pseudo\-aléatoire|[\<caps:sentence id\="tgt141" sentenceid\="00574fde17be9de3e07567ef5abe0110" class\="tgtSentence"\>System::Random Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.random.aspx)|  
|[rint, rintf, rintl](../c-runtime-library/reference/rint-rintf-rintl.md)|Arrondir à l'entier le plus proche au format à virgule flottante|[\<caps:sentence id\="tgt143" sentenceid\="1c04aeb4aeff1752cb65adabcee29f53" class\="tgtSentence"\>System::Math::Round\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.round.aspx)|  
|[\_rotl, \_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|Décaler `unsigned int` vers la gauche \(`_rotl`\) ou la droite \(`_rotr`\)|Non applicable.|  
|[\_scalb](../c-runtime-library/reference/scalb.md)|Mettre à l'échelle l'argument à la puissance 2|Non applicable.|  
|[scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl](../c-runtime-library/reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md)|Multiplier par la puissance intégrale de `FLT_RADIX`|Non applicable.|  
|[scanf, wscanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md), [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)|Lire les données dans `stdin` selon le format spécifié et écrire les données à l'emplacement spécifié|[System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx), [System::Console::ReadLine](https://msdn.microsoft.com/en-us/library/system.console.readline.aspx)|  
|[\_set\_controlfp](../c-runtime-library/reference/set-controlfp.md)|Définir une nouvelle valeur de mot de contrôle|Non applicable.|  
|[sin, sinf, sinh, sinhf](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|Calculer le sinus ou le sinus hyperbolique|[System::Math::Sin](https://msdn.microsoft.com/en-us/library/system.math.sin.aspx), [System::Math::Sinh](https://msdn.microsoft.com/en-us/library/system.math.sinh.aspx)|  
|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|Trouver la racine carrée|[\<caps:sentence id\="tgt162" sentenceid\="1a91af0bd8c63b4be64c7a0bec8dc8c4" class\="tgtSentence"\>System::Math::Sqrt\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.sqrt.aspx)|  
|[srand](../c-runtime-library/reference/srand.md)|Initialiser des séries pseudo\-aléatoires|[\<caps:sentence id\="tgt165" sentenceid\="00574fde17be9de3e07567ef5abe0110" class\="tgtSentence"\>System::Random Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.random.aspx)|  
|[\_status87, \_statusfp, \_statusfp2](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|Obtenir le mot d'état à virgule flottante|Non applicable.|  
|[strtod, \_strtod\_l, wcstod, \_wcstod\_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|Convertir une chaîne de caractères en valeur double précision|[\<caps:sentence id\="tgt169" sentenceid\="363f8f2cb09f8ca850491a65df66522e" class\="tgtSentence"\>System::Convert::ToDouble\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)|  
|[tan, tanf, tanh, tanhf](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|Calculer la tangente ou la tangente hyperbolique|[System::Math::Tan](https://msdn.microsoft.com/en-us/library/system.math.tan.aspx), [System::Math::Tanh](https://msdn.microsoft.com/en-us/library/system.math.tanh.aspx)|  
  
## Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)