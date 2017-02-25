---
title: "Pages de codes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.international"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ANSI (C++), pages de codes"
  - "jeux de caractères (C++), pages de codes"
  - "pages de codes (C++), types de"
  - "pages de codes de paramètres régionaux (C++)"
  - "localisation (C++), pages de codes"
  - "pages de codes multioctets (C++)"
  - "page de code du système par défaut"
ms.assetid: 4a26fc42-185a-4add-98bf-a7b314ae6186
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Pages de codes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un `code page` est un jeu de caractères, qui peut inclure des nombres, des signes de ponctuation, et d'autres glyphes.  Différentes langues et locations peuvent utiliser différentes pages de codes.  Par exemple, la page de codes ANSI 1252 est utilisée par l'anglais et la plupart des langues européennes; la page de codes OEM 932 est utilisée pour le kanji \(japonais\).  
  
 Une page de code peut être représentée dans une table comme mapping des caractères aux valeurs codées sur un octet ou des valeurs multioctets.  De nombreuses pages de codes partagent le jeu de caractères ASCII pour les caractères dans la plage 0x00 – 0x7F.  
  
 La bibliothèque Runtime de Microsoft utilise les types de pages de codes suivants:  
  
-   page de code du système ANSI par défaut:  Par défaut, lors du démarrage le système d'exécution définit automatiquement la page de codes multioctets de la page de codes ANSI de défaut du système, qui est obtenue à partir du système d'exploitation.  L'appel :  
  
    ```  
    setlocale ( LC_ALL, "" );  
    ```  
  
     définit également les paramètres régionaux et la page de codes ANSI de défaut du système..  
  
-   page de codes de paramètres régionaux  Le comportement d'une série de routines de service dépend des paramètres régionaux actuels, qui incluent la page de codes des paramètres régionaux. \(Pour plus d'informations, consultez [Routines dépendantes les paramètres régionaux](../c-runtime-library/locale.md).\) Par défaut, toutes les routines dépendantes les paramètres régionaux de la bibliothèque Runtime de Microsoft utilisent la page de codes qui correspond aux paramètres régionaux "C".  Au moment de l'exécution vous pouvez modifier ou interroger la page de codes des paramètres régionaux utilisés par un appel à [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
-   pages de codes multioctets  Le comportement de la plupart des routines de caractères multi\-octets dans la bibliothèque d'exécutables dépend des paramètres de la page multioctets actuels de code.  Par défaut, ces routines utilisent la page de codes ANSI de défaut du système.  Au moment de l'exécution vous pouvez interroger et modifier la page de codes multioctets avec [\_getmbcp](../c-runtime-library/reference/getmbcp.md) et [\_setmbcp](../c-runtime-library/reference/setmbcp.md), respectivement.  
  
-   Les paramètres régionaux "C" sont définis par ANSI pour correspondre aux paramètres régionaux dans lesquels les programmes C sont traditionnellement éxécuté.  La page de codes pour les paramètres régionaux "C" \(page de codes "C"\) correspond au jeu de caractères ASCII.  Par exemple, dans les paramètres régionaux "C" `islower` retourne la valeur true pour les valeurs 0x61 – 0x7A uniquement.  Pour les autres paramètres régionaux, `islower` peut retourner la valeur true pour ceux\-ci ainsi que d'autres valeurs, comme défini par les paramètres régionaux.  
  
## Voir aussi  
 [Internationalisation](../c-runtime-library/internationalization.md)   
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)