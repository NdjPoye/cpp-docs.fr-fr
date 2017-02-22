---
title: "Traitement des exceptions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.exceptions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO (Data Access Objects), exceptions"
  - "exception (macros)"
  - "exceptions, levées (MFC) (fonctions)"
  - "exceptions, traiter"
  - "macros, gestion des exceptions"
  - "MFC, exceptions"
  - "exceptions OLE, MFC (fonctions)"
  - "fonctions d'arrêt, MFC"
ms.assetid: 26d4457c-8350-48f5-916e-78f919787c30
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Traitement des exceptions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lorsqu'un programme s'exécute, de nombreuses conditions et erreurs anormales appelées « exceptions » peuvent se produire.  Celles\-ci peuvent inclure une mémoire insuffisante, des erreurs d'allocation de ressources, et des échecs de recherches de fichiers.  
  
 La bibliothèque MFC utilise un modèle de gestion des exceptions qui est modelisé étroitement à partir de celui proposé par le comité de normes ANSI pour C\+\+.  Un gestionnaire d'exceptions doit être installé avant d'appeler une fonction qui peut connaître une situation anormale.  Si la fonction rencontre une anomalie, elle lève une exception et le contrôle est passé au gestionnaire des exceptions.  
  
 Plusieurs macros incluses dans la bibliothèque MFC installeront les gestionnaires d'exceptions.  Plusieurs autres fonctions globales aident à lever des exceptions spécialisées et arrêter les programmes, si nécessaire.  Ces macros et fonctions globales sont classées dans les catégorier suivantes:  
  
-   [Macros d'exception](#_mfc_exception_macros), qui structurent votre gestionnaire des exceptions.  
  
-   [Fonctions de levées d'exceptions](#_mfc_exception.2d.throwing_functions), qui génèrent des exceptions de types spécifiques.  
  
-   [Fonctions d'arrêt](#_mfc_termination_functions), qui provoquent l'arrêt du programme.  
  
 Pour des exemples et plus d'informations, consultez l'article [Exceptions](../../mfc/exception-handling-in-mfc.md).  
  
### Macros d'Exceptions  
  
|||  
|-|-|  
|[TRY](../Topic/TRY.md)|Indique un bloc de code pour le traitement d'exceptions.|  
|[CATCH](../Topic/CATCH.md)|Indique un bloc de code pour intercepter une exception du bloc précédent de **TRY**.|  
|[CATCH\_ALL](../Topic/CATCH_ALL.md)|Indique un bloc de code pour intercepter toutes les exceptions du bloc précédent de **TRY**.|  
|[AND\_CATCH](../Topic/AND_CATCH.md)|Indique un bloc de code pour intercepter des exceptions supplémentaires du bloc précédent de **TRY**.|  
|[AND\_CATCH\_ALL](../Topic/AND_CATCH_ALL.md)|Définit un bloc de code pour intercepter tous les autres types d'exception supplémentaires levés dans un bloc précédent de **TRY**.|  
|[END\_CATCH](../Topic/END_CATCH.md)|Termine le dernier **CATCH** ou bloc de code d' `AND_CATCH`.|  
|[END\_CATCH\_ALL](../Topic/END_CATCH_ALL.md)|Arrête le dernier bloc de code d' `CATCH_ALL`.|  
|[THROW](../Topic/THROW%20\(MFC\).md)|Lève une exception spécifiée.|  
|[THROW\_LAST](../Topic/THROW_LAST.md)|Lève l'exception actuellement gérée au gestionnaire externe suivant.|  
  
### Fonctions de levées d'exceptions  
  
|||  
|-|-|  
|[AfxThrowArchiveException](../Topic/AfxThrowArchiveException.md)|Lève une exception d'archive.|  
|[AfxThrowFileException](../Topic/AfxThrowFileException.md)|Lève une exception de fichier.|  
|[AfxThrowMemoryException](../Topic/AfxThrowMemoryException.md)|Lève une exception de mémoire.|  
|[AfxThrowNotSupportedException](../Topic/AfxThrowNotSupportedException.md)|Lève une exception non prise en charge.|  
|[AfxThrowResourceException](../Topic/AfxThrowResourceException.md)|Lève une exception: ressource Windows non détectée.|  
|[AfxThrowUserException](../Topic/AfxThrowUserException.md)|Lève une exception dans une action de programme initiée par un utilisateur.|  
  
 MFC fournit deux fonctions de levées d'exceptions spécifiques aux exceptions OLE:  
  
### Fonctions d'exception OLE  
  
|||  
|-|-|  
|[AfxThrowOleDispatchException](../Topic/AfxThrowOleDispatchException.md)|Lève une exception dans une fonction automation OLE.|  
|[AfxThrowOleException](../Topic/AfxThrowOleException.md)|Lève une exception OLE.|  
  
 Pour prendre en charge les exceptions de base de données, les classes de base de données fournissent deux classes d'exception, `CDBException` et `CDaoException` et des fonctions globales pour prendre en charge les types d'exception:  
  
### Fonctions d'exception DAO  
  
|||  
|-|-|  
|[AfxThrowDAOException](../Topic/AfxThrowDaoException.md)|Lève une [CDaoException](../../mfc/reference/cdaoexception-class.md) de votre propre code.|  
|[AfxThrowDBException](../Topic/AfxThrowDBException.md)|Lève une [CDBException](../../mfc/reference/cdbexception-class.md) de votre propre code.|  
  
 MFC fournit la fonction suivante d'arrêt :  
  
### Fonctions d'Arrêt  
  
|||  
|-|-|  
|[AfxAbort](../Topic/AfxAbort.md)|Appelée pour mettre fin à une application lorsqu'une erreur irrécupérable se produit.|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)   
 [CException Class](../../mfc/reference/cexception-class.md)