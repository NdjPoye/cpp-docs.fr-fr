---
title: "Gestion des exceptions dans MFC | Microsoft Docs"
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
  - "exécution de programme anormale (C++)"
  - "archive (exceptions) (C++)"
  - "assertions (C++), quand utiliser les exceptions"
  - "Automation (C++), exceptions"
  - "gestion d'exceptions C++, activer"
  - "gestion d'exceptions C++, applications MFC"
  - "gestion d'exceptions C++, types de"
  - "bibliothèques de classes (C++), exceptions, prise en charge"
  - "DAO (C++), exceptions"
  - "exceptions, base de données (C++)"
  - "gestion des erreurs (C++), exceptions et"
  - "erreurs (C++), détectées par les assertions"
  - "gestion des exceptions (C++), MFC"
  - "exception (macros) (C++)"
  - "exceptions (C++), macros MFC et mots clés C++"
  - "appels de fonction, résultats"
  - "mots clés (C++), gestion des exceptions"
  - "macros (C++), gestion des exceptions"
  - "macros (C++), MFC (exception) (macros)"
  - "mémoire (C++), out_of_memory (exceptions)"
  - "MFC (C++), exceptions"
  - "ODBC (exceptions) (C++)"
  - "OLE (exceptions) (C++), gestion des exceptions MFC"
  - "out_of_memory (exceptions) (C++)"
  - "exceptions définies (C++)"
  - "requêtes de services non pris en charge"
  - "exception d'allocation des ressources"
  - "ressources (C++), allouer"
  - "sérialisation (C++), exceptions"
  - "Windows (C++), exceptions d'allocation des ressources"
ms.assetid: 0926627d-2ba7-44a6-babe-d851a4a2517c
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Gestion des exceptions dans MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique les mécanismes de gestion des exceptions disponibles dans MFC.  Deux mécanismes sont disponibles :  
  
-   Exceptions C\+\+, disponibles dans la version 3,0 de MFC et ses versions ultérieures  
  
-   Les macros exception de MFC, disponibles dans les versions 1,0 de MFC et ses versions ultérieures  
  
 Si vous écrivez une application à l'aide de MFC, vous devez utiliser un mécanisme C\+\+.  Utilisez le mécanisme basé sur une macro si votre application existante utilise déjà ce mécanisme de manière intensive.  
  
 Convertissez facilement le code existant pour utiliser des exceptions C\+\+ au lieu de macros d'exception MFC.  Les avantages de convertir votre code et des conseils pour cela sont décrites dans l'article [Exceptions : conversion à partir de macros d'exception MFC](../mfc/exceptions-converting-from-mfc-exception-macros.md).  
  
 Si vous avez déjà une application développée à l'aide des macros exception MFC, vous pouvez continuer à utiliser les macros dans votre code existant, tout en utilisant des exceptions C\+\+ dans votre nouveau code.  L'article [Exceptions : modifications apportées aux macros d'exception dans la version 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md) fournit des instructions pour effectuer cette opération.  
  
> [!NOTE]
>  Pour activer la gestion des exceptions C\+\+ dans votre code, sélectionnez activer les exceptions C\+\+ dans la page de génération de code dans le dossier C\/C\+\+ de la boîte de dialogue [Pages de propriétés](../ide/property-pages-visual-cpp.md) du projet, ou utilisez l'option \/GX du compilateur.  La valeur par défaut est \/GX, qui désactive la gestion des exceptions.  
  
 Cet article couvre les rubriques suivantes :  
  
-   [Quand utiliser les exceptions](#_core_when_to_use_exceptions)  
  
-   [Prise en charge des exceptions MFC](#_core_mfc_exception_support)  
  
-   [Plus de lecture sur les exceptions](#_core_further_reading_about_exceptions)  
  
##  <a name="_core_when_to_use_exceptions"></a> Quand utiliser les exceptions  
 Trois catégories de résultats peuvent se produire lorsqu'une fonction est appelée pendant l'exécution du programme : exécution normale, exécution incorrecte, ou exécution anormale.  Chaque catégorie est décrite ci\-dessous.  
  
-   Exécution normale  
  
     La fonction peut s'exécuter normalement et retourner.  Certaines fonctions retournent un code de sortie pour l'appelant, qui indique le résultat de la fonction.  Les codes de sortie possibles sont strictement définis pour la fonction et représentent la plage de résultats possibles de la fonction.  Le code de sortie peut indiquer une réussite ou un échec ou même peut indiquer un type spécial d'échec qui est compris dans la plage régulière des attentes.  Par exemple, une fonction d'état de fichier peut retourner un code qui indique que le fichier n'existe pas.  Notez que le terme « code d'erreur » n'est pas utilisé car le code de sortie représente un des nombreux résultats attendus.  
  
-   Exécution incorrecte  
  
     L'appelant commet une certaine erreur en passant des arguments à la fonction ou en appellant la fonction dans un environnement inapproprié.  Cette situation entraîne une erreur, elle doit être détectée par une assertion lors du développement du programme. \(Pour plus d'informations sur les assertions, consultez [Assertions C\/C\+\+](../Topic/C-C++%20Assertions.md)\).  
  
-   Exécution anormale  
  
     L'exécution anormale inclut des situations où les conditions extérieures au contrôle du programme, telles que la mémoire insuffisante ou les erreurs d'E\/S, influencent les résultats de la fonction.  Les situations anormales doivent être gérées en interceptant et en levant des exceptions.  
  
 L'Utilisation des exceptions est particulièrement appropriée pour l'exécution anormale.  
  
##  <a name="_core_mfc_exception_support"></a> Prise en charge des exceptions MFC  
 Si vous utilisez des exceptions C\+\+ directement ou utilisez les macros exceptions de MFC, vous allez utiliser des objets dérivés de [CException Class](../mfc/reference/cexception-class.md) ou `CException` qui peuvent être levés par l'infrastructure ou par votre application.  
  
 Le tableau ci\-dessous indique les exceptions prédéfinies fournies par MFC.  
  
|Classe d'exceptions|Signification|  
|-------------------------|-------------------|  
|[CMemoryException Class](../mfc/reference/cmemoryexception-class.md)|Mémoire insuffisante.|  
|[CFileException Class](../mfc/reference/cfileexception-class.md)|Exception de fichier|  
|[CArchiveException Class](../mfc/reference/carchiveexception-class.md)|Exception d'archive sérialisation\/|  
|[CNotSupportedException Class](../mfc/reference/cnotsupportedexception-class.md)|Réponse à la demande de service non pris en charge|  
|[CResourceException Class](../mfc/reference/cresourceexception-class.md)|Exception d'allocation des ressources windows|  
|[CDaoException Class](../mfc/reference/cdaoexception-class.md)|Exceptions de base de données \(classes DAO\)|  
|[CDBException Class](../mfc/reference/cdbexception-class.md)|Exceptions de base de données \(classes ODBC\)|  
|[COleException Class](../mfc/reference/coleexception-class.md)|Exceptions OLE|  
|[COleDispatchException Class](../mfc/reference/coledispatchexception-class.md)|Exceptions d'envoi \(automation\)|  
|[CUserException Class](../mfc/reference/cuserexception-class.md)|Exception qui avertit l'utilisateur avec un message, puis génère un [CException Class](../mfc/reference/cexception-class.md) générique|  
  
> [!NOTE]
>  MFC prend en charge à la fois les exceptions C\+\+ les macros exceptions MFC.  MFC ne prend pas directement en charge les gestionnaires des exceptions structurées par Windows NT \(SEH\), comme décrit dans [Gestion des exceptions structurées](http://msdn.microsoft.com/library/windows/desktop/ms680657).  
  
##  <a name="_core_further_reading_about_exceptions"></a> Plus de lecture sur les exceptions  
 Les articles suivants expliquent l'utilisation de la bibliothèque MFC pour la gestion d'exceptions :  
  
-   [Exceptions : interception et suppression d'exceptions](../mfc/exceptions-catching-and-deleting-exceptions.md)  
  
-   [Exceptions : examen du contenu des exceptions](../mfc/exceptions-examining-exception-contents.md)  
  
-   [Exceptions : libération d'objets dans les exceptions](../mfc/exceptions-freeing-objects-in-exceptions.md)  
  
-   [Exceptions : levée d'exceptions à partir de vos propres fonctions](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)  
  
-   [Exceptions : exceptions de base de données](../mfc/exceptions-database-exceptions.md)  
  
-   [Exceptions : exceptions OLE](../mfc/exceptions-ole-exceptions.md)  
  
 Les éléments suivants comparent les macros exceptions de MFC par les mots clés d'exception C\+\+ et expliquent comment vous pouvez ajuster votre code :  
  
-   [Exceptions : modifications apportées aux macros d'exception dans la version 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)  
  
-   [Exceptions : conversion à partir de macros d'exception MFC](../mfc/exceptions-converting-from-mfc-exception-macros.md)  
  
-   [Exceptions : utilisation de macros MFC et d'exceptions C\+\+](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)  
  
## Voir aussi  
 [Gestion d'exceptions C\+\+](../cpp/cpp-exception-handling.md)   
 [Comment faire pour : Créer mes propres Classes Exception personnalisées ?](http://go.microsoft.com/fwlink/?LinkId=128045)