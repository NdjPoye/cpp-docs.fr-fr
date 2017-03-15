---
title: "Exceptions&#160;: modifications apport&#233;es aux macros d&#39;exception dans la version&#160;3.0 | Microsoft Docs"
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
  - "gestion d'exceptions C++, éléments à prendre en considération lors de la mise à niveau"
  - "CATCH (macro)"
  - "exceptions, nouveautés"
  - "THROW_LAST (macro)"
ms.assetid: 3aa20d8c-229e-449c-995c-ab879eac84bc
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Exceptions&#160;: modifications apport&#233;es aux macros d&#39;exception dans la version&#160;3.0
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ceci est une rubrique avancée.  
  
 Dans la version 3,0 de MFC et versions ultérieures, les macros de gestion des exceptions ont été modifiées pour utiliser des exceptions C\+\+.  Cet article indique que ces modifications peuvent affecter le comportement de code existant utilisant des macros.  
  
 Cet article couvre les rubriques suivantes:  
  
-   [Types d'exception et la macro CATCH](#_core_exception_types_and_the_catch_macro)  
  
-   [Re\-lever des exceptions](#_core_re.2d.throwing_exceptions)  
  
##  <a name="_core_exception_types_and_the_catch_macro"></a> Types d'exception et la macro CATCH  
 Dans les versions antérieures de MFC, la macro **CATCH** a utilisé les informations de type d'exécution de MFC pour déterminer le type d'exception ; le type d'exception est déterminé, en d'autres termes, au site de CATCH.  Avec les exceptions C\+\+, toutefois, le type d'exception est toujours déterminé au site de jet par le type de l'objet exception qui est levé.  Vous obtiendrez des incompatibilités dans le cas rare où le type de pointeur à l'objet levé est différent du type de l'objet levé.  
  
 L'exemple suivant illustre la conséquence de cette différence entre la version 3.0 de MFC et les versions antérieures :  
  
 [!code-cpp[NVC_MFCExceptions#1](../mfc/codesnippet/CPP/exceptions-changes-to-exception-macros-in-version-3-0_1.cpp)]  
  
 Ce code se comporte différemment dans la version 3.0 parce que le contrôle est toujours passé au premier bloc **catch**  avec une exception\-déclaration correspondante.  Le résultat de l'expression throw.  
  
 [!code-cpp[NVC_MFCExceptions#19](../mfc/codesnippet/CPP/exceptions-changes-to-exception-macros-in-version-3-0_2.cpp)]  
  
 est retourné comme **CException\***, bien qu'il soit construit comme **CCustomException**.  La macro **CATCH** dans les versions 2.5 de MFC et antérieur utilise `CObject::IsKindOf` pour tester le type au moment de l'exécution.  Parce que l'expression  
  
 [!code-cpp[NVC_MFCExceptions#20](../mfc/codesnippet/CPP/exceptions-changes-to-exception-macros-in-version-3-0_3.cpp)]  
  
 est true, le premier bloc catch capture l'exception.  Dans 3.0, qui utilise des exceptions C\+\+ pour implémenter plusieurs macros de gestion des exceptions, le second bloc catch correspond à la `CException`levée.  
  
 Du code comme ceci est rare.  Elle apparaît généralement lorsque objet exception transmis à une autre fonction qui reçoit un **CException\***générique, effectue « avant » THROW traitement, et enfin lève l'exception.  
  
 Pour contourner ce problème, déplacez l'expression de jet de la fonction au code appelant et levez une exception du type réel connu du compilateur lorsque l'exception est générée.  
  
##  <a name="_core_re.2d.throwing_exceptions"></a> Re\-lever des exceptions  
 Un bloc catch ne peut pas lever le même pointeur d'exception qu'il a intercepté.  
  
 Par exemple, le code n'est pas valide dans les versions précédentes, mais génère des résultats inattendus avec la version 3.0 :  
  
 [!code-cpp[NVC_MFCExceptions#2](../mfc/codesnippet/CPP/exceptions-changes-to-exception-macros-in-version-3-0_4.cpp)]  
  
 L'utilisation de **THROW** dans le bloc catch provoque la suppression du pointeur `e` , de sorte que le site catch externe de recevoir un pointeur invalide.  Utilisez `THROW_LAST` pour re\-lever `e`.  
  
 Pour plus d'informations, consultez [Exceptions : Interception et suppression des exceptions](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
## Voir aussi  
 [Gestion des exceptions](../mfc/exception-handling-in-mfc.md)