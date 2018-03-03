---
title: "Exceptions : Interception et suppression d’Exceptions | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- exceptions [MFC], deleting
- AND_CATCH macro [MFC]
- try-catch exception handling [MFC], catching and deleting exceptions
- exception handling [MFC], catching and deleting exceptions
- catch blocks [MFC], catching and deleting exceptions
- execution [MFC], returns from within catch block
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8496b5228fe4002bb1ca80f8fbe793fd5e16ca81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>Exceptions : interception et suppression d'exceptions
Les instructions et les exemples suivants montrent comment intercepter et supprimer des exceptions. Pour plus d’informations sur la **essayez**, **catch**, et `throw` mots clés, consultez [gestion des exceptions C++](../cpp/cpp-exception-handling.md).  
  
 Vos gestionnaires d’exceptions doivent supprimer des objets d’exception qu’ils gèrent, car l’échec de suppression de l’exception entraîne une fuite de mémoire chaque fois que ce code intercepte une exception.  
  
 Votre **catch** bloc doit supprimer une exception lorsque :  
  
-   Le **catch** bloc lève une exception.  
  
     Bien entendu, vous ne devez pas supprimer l’exception si vous levez de nouveau la même exception :  
  
     [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]  
  
-   L’exécution retourne depuis le **catch** bloc.  
  
> [!NOTE]
>  Lorsque vous supprimez un `CException`, utiliser le **supprimer** fonction membre à supprimer de l’exception. N’utilisez pas le **supprimer** (mot clé), car elle peut échouer si l’exception n’est pas sur le tas.  
  
#### <a name="to-catch-and-delete-exceptions"></a>Pour intercepter et supprimer des exceptions  
  
1.  Utilisez le **essayez** mot clé pour configurer un **essayez** bloc. Exécuter les instructions de programme qui peuvent lever une exception dans un **essayez** bloc.  
  
     Utilisez le **catch** mot clé pour configurer un **catch** bloc. Placez le code de gestion des exceptions dans une **catch** bloc. Le code dans le **catch** bloc est exécuté uniquement si le code dans le **essayez** bloc lève une exception du type spécifié dans le **catch** instruction.  
  
     Le squelette ci-dessous comment **essayez** et **catch** disposition habituelle des blocs :  
  
     [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]  
  
     Lorsqu’une exception est levée, le contrôle passe à la première **catch** bloc dont déclaration d’exception correspond au type de l’exception. Vous pouvez gérer de manière sélective différents types d’exceptions avec séquentiel **catch** bloque comme indiqué ci-dessous :  
  
     [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]  
  
 Pour plus d’informations, consultez [Exceptions : conversion à partir de Macros d’Exception MFC](../mfc/exceptions-converting-from-mfc-exception-macros.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion des exceptions](../mfc/exception-handling-in-mfc.md)

