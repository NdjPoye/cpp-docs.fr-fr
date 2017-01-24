---
title: "Win32 Predefined Symbols | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Win32 [C++], predefined symbols"
  - "symbols, Win32 predefined"
  - "Windows API [C++], predefined symbols"
ms.assetid: 45c8e193-ee2a-4024-bfc2-34d1ec9c9239
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Win32 Predefined Symbols
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces symboles sont définis dans les fichiers d'en\-tête Win32 et ils prennent en charge les fonctions et les actions standard des applications Windows.  Ces symboles sont principalement utilisés avec les éléments d'interface utilisateur courants.  Lorsque vous utilisez des contrôles dans les éditeurs de ressources, ces symboles s'affichent dans la [fenêtre Propriétés](../Topic/Properties%20Window.md) associée à ces contrôles courants.  Par exemple, si votre barre d'outils doit afficher l'icône de l'application, l'icône est associée au symbole IDI\_SMALL dans la fenêtre Propriétés.  
  
|||  
|-|-|  
|IDABORT|Contrôle : bouton Abandonner d'une boîte de dialogue|  
|IDC\_STATIC|Contrôle : texte statique dans une boîte de dialogue|  
|IDCANCEL|Contrôle : bouton Annuler d'une boîte de dialogue|  
|IDD\_ABOUTBOX|Boîte de dialogue : boîte de dialogue À propos de produit|  
|IDI\_PROJECTNAME|Icône : icône du projet actuel|  
|IDI\_SMALL|Icône : petite icône du projet actuel|  
|IDIGNORE|Contrôle : utilisé avec le bouton Ignorer dans les boîtes de dialogue|  
|IDM\_ABOUT|Élément de menu : utilisé avec Aide...À propos de...|  
|IDM\_EXIT|Élément de menu : utilisé avec Fichier...Quitter...|  
|IDNO|Contrôle : bouton Non d'une boîte de dialogue|  
|IDOK|Contrôle : bouton OK d'une boîte de dialogue|  
|IDRETRY|Contrôle : bouton Réessayer d'une boîte de dialogue|  
|IDS\_APP\_TITLE|Chaîne : nom actuel de l'application|  
|IDYES|Contrôle : bouton Oui d'une boîte de dialogue|  
  
## Configuration requise  
 Win32  
  
## Voir aussi  
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)