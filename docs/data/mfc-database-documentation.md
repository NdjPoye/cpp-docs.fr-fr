---
title: "Documentation des bases de donn&#233;es MFC | Microsoft Docs"
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
  - "DAO (C++), MFC"
  - "bases de données (C++), MFC"
  - "MFC (C++), applications de bases de données"
  - "ODBC (C++), MFC"
ms.assetid: bb120282-cd0d-4bf4-a27c-93b3501fb3a0
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Documentation des bases de donn&#233;es MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La documentation MFC des classes DAO et ODBC comprend les composants énumérés dans le tableau suivant.  
  
### Documentation des bases de données MFC  
  
|Pour la documentation à propos de|Consultez|  
|---------------------------------------|---------------|  
|Classes DAO et ODBC|Le nom de la classe dans *MFC Reference*|  
|Fonctions globales et macros DAO et ODBC|Le nom de la fonction ou de la macro dans *MFC Reference*|  
|Programmation à l'aide des classes ODBC MFC|[ODBC et MFC](../data/odbc/odbc-and-mfc.md)|  
|Notes techniques pour DAO et ODBC|[MFC Technical Notes](../mfc/technical-notes-by-category.md)|  
  
##  <a name="_core_mfc_documentation_and_dao_documentation"></a> Documentation MFC et Documentation DAO  
 Dans la documentation MFC pour les classes DAO MFC, vous trouverez des références à des rubriques dans la documentation du kit de développement DAO SDK, inclus dans la documentation en ligne.  Dans la mesure où MFC encapsule \(ou enveloppe\), DAO, la documentation MFC :  
  
-   Met l'accent sur MFC et la manière dont cette bibliothèque diffère de l'implémentation DAO sous\-jacente.  
  
-   Renvoie à des rubriques d'aide du kit de développement DAO SDK pour les détails sous\-jacents.  Ces références croisées sont toujours indiquées sous la forme « rubrique *X* dans l'aide de DAO ».  
  
-   Souligne les cas où MFC se comporte différemment de DAO.  MFC n'encapsule pas entièrement DAO.  Par exemple, MFC ne fournit pas d'objets pour la fonction de sécurité DAO.  
  
> [!NOTE]
>  L'aide du kit de développement DAO SDK est un fichier d'aide séparé.  Cette documentation ne contient pas de liens hypertexte vers l'aide de DAO dans cette version de Visual C\+\+.  
  
> [!NOTE]
>  Vous aurez peut\-être un travail de traduction à faire en parcourant les rubriques dans l'aide du kit de développement DAO SDK.  Les exemples fournis dans la documentation principale du kit DAO SDK sont écrits non pas en C\+\+ mais en langage de programmation Basic. \(Le kit de développement DAO SDK fournit, cependant, un ensemble d'exemples C\+\+ qui n'utilisent pas les MFC.\)  
  
##  <a name="_core_mfc_documentation_and_odbc_documentation"></a> Documentation MFC et documentation ODBC  
 La documentation MFC pour les classes ODBC MFC est structurée différemment.  Les classes ODBC MFC fournissent une abstraction de haut niveau qui repose sur ODBC à la place d'un wrapper de l'API ODBC.  Par conséquent, les deux jeux de documentation sont moins liés que ne le sont les jeux de documentation MFC et DAO.  La documentation ODBC utilise le langage C, qui est plus proche de C\+\+ que ne l'est Basic.  
  
## Voir aussi  
 [Classes de bases de données MFC \(ODBC et DAO\)](../data/mfc-database-classes-odbc-and-dao.md)   
 [Éléments fondamentaux relatifs à ODBC](../data/odbc/odbc-basics.md)