---
title: "Gestion d&#39;exceptions C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestion d'exceptions C++"
  - "Visual C++, gestion des exceptions"
ms.assetid: 65f80b44-9d0f-4d17-b910-07205a5c5c40
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestion d&#39;exceptions C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le langage C\+\+ fournit une prise en charge intégrée des levées et des interceptions d'exceptions.  Lorsque vous programmez en C\+\+, vous devez presque toujours utiliser la prise en charge intégrée des exceptions C\+\+, comme décrit dans cette section.  
  
 Pour activer la gestion des exceptions C\+\+ dans votre code, utilisez [\/EHsc](../build/reference/eh-exception-handling-model.md).  
  
## Dans cette section  
 Cette discussion sur la gestion des exceptions C\+\+ comprend ce qui suit :  
  
-   [Instructions try, catch et throw](../cpp/try-throw-and-catch-statements-cpp.md)  
  
-   [Évaluation des blocs CATCH](../cpp/how-catch-blocks-are-evaluated-cpp.md)  
  
-   [Exceptions et déroulement de la pile](../cpp/exceptions-and-stack-unwinding-in-cpp.md)  
  
-   [Spécifications des exceptions](../cpp/exception-specifications-throw-cpp.md)  
  
-   [noexcept](../cpp/noexcept-cpp.md)  
  
-   [Exceptions C\+\+ non gérées](../cpp/unhandled-cpp-exceptions.md)  
  
-   [Mélange d'exceptions C \(structurées\) et d'exceptions C\+\+](../cpp/mixing-c-structured-and-cpp-exceptions.md)  
  
## Prise en charge des anciennes exceptions MFC  
 Depuis la version 4.0, MFC utilise le mécanisme de gestion des exceptions C\+\+.  Bien qu'il soit conseillé d'utiliser la gestion des exceptions C\+\+ dans votre nouveau code, MFC 4.0 et les versions ultérieures ont conservé les macros des versions antérieures, de sorte que l'ancien code soit toujours valable.  Les macros et le nouveau mécanisme peuvent également être combinés.  Pour plus d'informations sur les mélanges de macros et sur la gestion des exceptions C\+\+, ainsi que sur la conversion d'ancien code pour utiliser le nouveau mécanisme, consultez les articles [Exceptions : Utilisation de la macro MFC et des exceptions C\+\+](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) et [Exceptions : Conversion des macros d'exceptions MFC](../mfc/exceptions-converting-from-mfc-exception-macros.md).  Les anciennes macros d'exceptions MFC, si vous les utilisez toujours, correspondent aux mots clés d'exception C\+\+.  Consultez [Exceptions : Modifications apportées aux macros d'exceptions dans la version 3.0 \(MFC\)](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md).  
  
## Voir aussi  
 [Gestion des exceptions](../cpp/exception-handling-in-visual-cpp.md)