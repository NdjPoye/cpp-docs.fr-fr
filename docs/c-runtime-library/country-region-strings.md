---
title: "Cha&#238;nes pays/r&#233;gion | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
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
  - "C"
helpviewer_keywords: 
  - "chaînes pays/région"
ms.assetid: 5baf0ccf-0d9b-40dc-83bd-323705287930
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Cha&#238;nes pays/r&#233;gion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les chaînes de pays et de région peuvent être combinés avec une chaîne de langue pour créer une spécification de paramètres régionaux pour les fonctions `setlocale`, `_wsetlocale`, `_create_locale` et `_wcreate_locale`. Pour obtenir la liste des noms de pays\/région qui sont pris en charge par les différentes versions du système d’exploitation Windows, consultez les [Informations de référence de l’API NLS \(National Language Support\)](http://msdn.microsoft.com/goglobal/bb896001.aspx). Dans les listes, la chaîne de pays\/région peut être une des valeurs de la colonne **Locale – Language Country\/Region** ou une des abréviations de la colonne **Country or Region name abbreviation**.  
  
 L’implémentation de la bibliothèque Runtime C prend également en charge les chaînes et abréviations de pays\/région supplémentaires suivantes :  
  
|Chaîne de pays\/région|Abréviation|Nom des paramètres régionaux équivalents|  
|----------------------------|-----------------|----------------------------------------------|  
|america|USA|fr\-FR|  
|britain|GBR|en\-GB|  
|china|CHN|zh\-CN|  
|czech|CZE|cs\-CZ|  
|england|GBR|en\-GB|  
|great britain|GBR|en\-GB|  
|holland|NLD|NL\-NL|  
|hong\-kong|HKG|zh\-HK|  
|new\-zealand|NZL|en\-NZ|  
|nz|NZL|en\-NZ|  
|pr china|CHN|zh\-CN|  
|pr\-china|CHN|zh\-CN|  
|puerto\-rico|PRI|es\-PR|  
|slovak|SVK|sk\-SK|  
|south africa|ZAF|af\-ZA|  
|south korea|KOR|ko\-KR|  
|south\-africa|ZAF|af\-ZA|  
|south\-korea|KOR|ko\-KR|  
|trinidad & tobago|TTO|en\-TT|  
|uk|GBR|en\-GB|  
|united\-kingdom|GBR|en\-GB|  
|united\-states|USA|fr\-FR|  
|us|USA|fr\-FR|  
  
## Voir aussi  
 [Chaînes relatives aux noms, aux langues, au pays et à la région](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Chaînes de langue](../c-runtime-library/language-strings.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)