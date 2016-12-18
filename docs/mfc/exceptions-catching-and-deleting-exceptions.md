---
title: "Exceptions&#160;: interception et suppression d&#39;exceptions | Microsoft Docs"
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
  - "AND_CATCH (macro)"
  - "catch (blocs), intercepter et supprimer des exceptions"
  - "gestion des exceptions, intercepter et supprimer des exceptions"
  - "exceptions, supprimer"
  - "exécution, retours à partir de bloc Catch"
  - "try-catch (gestion des exceptions), intercepter et supprimer des exceptions"
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Exceptions&#160;: interception et suppression d&#39;exceptions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'instruction et les exemples suivants indiquent comment intercepter et supprimer des exceptions.  Pour plus d'informations sur **try**, **catch**, et les mots clés `throw`, consultez [Gestion des exceptions C\+\+](../cpp/cpp-exception-handling.md).  
  
 Les gestionnaires d'exceptions peuvent supprimer des objets d'exception qu'ils gèrent, car l'échec de la suppression de l'exception provoque une fuite de mémoire lorsque ce code d'intercepte une exception.  
  
 Le bloc **catch** doit supprimer une exception lorsque :  
  
-   Le bloc **catch** lève une exception.  
  
     Naturellement, vous ne devez pas supprimer l'exception si vous levez la même exception à nouveau :  
  
     [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/CPP/exceptions-catching-and-deleting-exceptions_1.cpp)]  
  
-   L'exécution retourne depuis le bloc **catch**.  
  
> [!NOTE]
>  En supprimant une `CException`, utilisez la fonction membre **Supprimer** pour supprimer l'exception.  N'utilisez pas le mot clé **supprimer**, car il peut échouer si l'exception ne se trouve pas sur le tas.  
  
#### Pour repérer et supprimer des exceptions  
  
1.  Utilisez le mot clé **try** pour installer un bloc **try**.  Exécutez les instructions de programmation qui peuvent lever une exception dans un bloc **try**.  
  
     Utilisez le mot clé **catch** pour installer un bloc **catch**.  Placez le code de gestion des exceptions dans un bloc **catch**.  Le code dans le bloc **catch** n'est exécuté que lorsque le code dans le bloc **try** lève une exception du type spécifié dans l'instruction **catch**.  
  
     La structure suivante montre comment **try** et les blocs **catch** sont normalement réorganisés :  
  
     [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/CPP/exceptions-catching-and-deleting-exceptions_2.cpp)]  
  
     Lorsqu'une exception est levée, le contrôle est passé au premier bloc **catch** dont la déclaration d'exception correspond au type de l'exception.  Vous pouvez sélectivement gérer différents types d'exceptions dans les blocs **catch** séquentiels comme indiqué ci\-dessous :  
  
     [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/CPP/exceptions-catching-and-deleting-exceptions_3.cpp)]  
  
 Pour plus d'informations, consultez [Exceptions : Conversion de macros d'exception MFC](../mfc/exceptions-converting-from-mfc-exception-macros.md).  
  
## Voir aussi  
 [Gestion des exceptions](../mfc/exception-handling-in-mfc.md)