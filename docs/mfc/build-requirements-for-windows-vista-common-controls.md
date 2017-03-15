---
title: "Configuration requise pour les contr&#244;les communs Windows Vista | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles communs (MFC)"
  - "contrôles communs (MFC), spécifications de build"
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Configuration requise pour les contr&#244;les communs Windows Vista
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La version 6.1 des contrôles communs Windows pris en charge dans la bibliothèque Microsoft Foundation Class \(MFC\).  Les contrôles communs sont inclus dans [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] et la bibliothèque est incluse dans [!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)].  La bibliothèque fournit de nouvelles méthodes qui améliorent les classes existantes, et les nouvelles classes et méthodes qui prennent en charge les contrôles communs [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)].  Lorsque vous créez votre application, vous devez respecter les exigences de compilation et de migration décrites dans les sections suivantes.  
  
## Spécifications de compilation  
  
### Versions prises en charge  
 Certaines nouvelles classes et méthodes ne prennent en charge que [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] et ses versions ultérieures, alors que d'autres méthodes prennent également en charge les systèmes d'exploitation antérieurs.  Une remarque dans la section de `Requirements` de chaque rubrique de la méthode spécifie si le système d'exploitation requis minimal est [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)].  
  
 Même si votre ordinateur n'est pas [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)], vous pouvez créer une application MFC pour les autres [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] si vous avez les fichiers d'en\-tête de MFC de la version 6.1 sur votre ordinateur.  Toutefois, les contrôles communs conçus spécifiquement pour [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] ne fonctionnent par sur ce système, et sont ignorés par les systèmes d'exploitation antérieurs.  
  
### Jeux de caractères pris en charge  
 Les nouveaux contrôles communs Windows ne prennent en charge que le jeu de caractères Unicode, et non le jeu de caractères ANSI.  Si vous créez votre application sur la ligne de commande, utilisez les deux options suivantes définies \(\/D\) du compilateur de la spécification Unicode en tant que jeu de caractères sous\-jacent :  
  
```  
/D_UNICODE /DUNICODE  
```  
  
 Si vous générez l'application dans l'environnement de développement intégré \(IDE\) Visual Studio, spécifiez l'option **Jeu de caractères Unicode** de la propriété **Jeu de caractères** dans le nœud **Général** des propriétés du projet.  
  
 La version ANSI de plusieurs méthodes MFC ont été déconseillées à compter de la version 6.1 des contrôles communs Windows.  Pour plus d'informations, consultez [API ANSI déconseillées](../mfc/deprecated-ansi-apis.md).  
  
## Spécifications de migration  
 Si vous utilisez l'IDE de Visual Studio pour créer une application MFC qui utilise la version 6.1 des contrôles communs Windows, l'IDE déclare automatiquement un manifeste approprié.  Toutefois, si vous migrez une application existante de MFC depuis une version antérieure de Visual Studio et que voulez utiliser les nouveaux contrôles communs, l'IDE ne fournit pas automatiquement les informations manifestes pour mettre à niveau votre application.  Au lieu de cela, vous devez manuellement insérer le code ci\-dessous dans votre fichier stdafx.h :  
  
```  
#ifdef UNICODE  
#if defined _M_IX86  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='x86' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#elif defined _M_IA64  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='ia64' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#elif defined _M_X64  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='amd64' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#else  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='*' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#endif  
#endif  
```  
  
## Voir aussi  
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)   
 [Graphique hiérarchique](../mfc/hierarchy-chart.md)   
 [API ANSI déconseillées](../mfc/deprecated-ansi-apis.md)