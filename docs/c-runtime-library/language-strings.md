---
title: "Cha&#238;nes de langue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.strings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "chaînes de langue"
ms.assetid: bbee63b1-af0b-4e44-9eaf-dd3e265c05fd
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# Cha&#238;nes de langue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fonctions `setlocale` et `_create_locale` peuvent utiliser les langages pris en charge par l'API Windows NLS sur les systèmes d'exploitation qui n'utilisent pas la page de codes Unicode.  Pour consulter une liste des langues prises en charge par différentes versions de systèmes d'exploitation, voir [Référence d'API de prise en charge de la langue \(NLS\)](http://msdn.microsoft.com/goglobal/bb896001.aspx).  La chaîne langue peut prendre n'importe quelle valeur des colonnes **Langage** et **Abréviation de nom de langue** venant de la liste des langues prises en charge.  L'implémentation de la bibliothèque runtime C prend également en charge ces chaînes langage :  
  
|Chaîne langage|Nom de paramètres régionaux équivalent|  
|--------------------|--------------------------------------------|  
|américain|en\-US|  
|anglais américain|en\-US|  
|anglais américain|en\-US|  
|australien|en\-AU|  
|belge|nl\-BE|  
|canadien|en\-CA|  
|chh|zh\-HK|  
|chi|zh\-SG|  
|chinois|zh|  
|chinois\-Hong Kong|zh\-HK|  
|chinois – simplifié|zh\-CN|  
|chinois\-Singapour|zh\-SG|  
|chinois\-traditionnel|zh\-TW|  
|néerlandais\-belge|nl\-BE|  
|anglais\-américain|en\-US|  
|anglais\-aus|en\-AU|  
|anglais\-Belize|en\-BZ|  
|anglais\-can|en\-CA|  
|anglais\-Caraïbes|en\-029|  
|anglais\-ire.|en\-IE|  
|anglais\-Jamaïque|en\-JM|  
|anglais\-nz|en\-NZ|  
|anglais\-Afrique du Sud|en\-ZA|  
|anglais\-Trinidad et Tobago|en\-TT|  
|anglais\-RU|en\-GB|  
|anglais\-usa|en\-US|  
|anglais\-usa|en\-US|  
|français\-belge|fr\-BE|  
|français\-canadien|fr\-CA|  
|français\-Luxembourg|fr\-LU|  
|français\-Suisse|fr\-CH|  
|allemand\-autrichien|de\-AT|  
|allemand\-Liechtenstein|de\-LI|  
|allemand\-Luxembourg|de\-LU|  
|allemand\-Suisse|de\-CH|  
|irlandais\-anglais|en\-IE|  
|italien\-Suisse|it\-CH|  
|norvégien|non|  
|norvégien\-Bokmal|nb\-NO|  
|norvégien\-Nynorsk|nn\-NO|  
|portugais\-brésilien|pt\-BR|  
|espagnol\-Argentine|es\-AR|  
|espagnol\-Bolivie|es\-BO|  
|espagnol\-Chili|es\-CL|  
|espagnol\-Colombie|es\-CO|  
|espagnol\-Costa Rica|es\-CR|  
|espagnol\-République dominicaine|es\-DO|  
|espagnol\-Équateur|es\-EC|  
|espagnol\-Salvador|es\-SV|  
|espagnol\-Guatemala|es\-GT|  
|espagnol\-Honduras|es\-HN|  
|espagnol\-mexicain|es\-MX|  
|espagnol\-moderne|es\-ES|  
|espagnol\-Nicaragua|es\-NI|  
|espagnol\-Panama|es\-PA|  
|espagnol\-Paraguay|es\-PY|  
|espagnol\-Pérou|es\-PE|  
|espagnol\-Porto Rico|es\-PR|  
|espagnol\-Uruguay|es\-UY|  
|espagnol\-Venezuela|es\-VE|  
|Suédois\-Finlande|sv\-FI|  
|Suisse|de\-CH|  
|uk|en\-GB|  
|us|en\-US|  
|Etats\-Unis|en\-US|  
  
## Voir aussi  
 [Chaînes relatives aux noms, aux langues, au pays et à la région](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Chaînes pays\/région](../c-runtime-library/country-region-strings.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)