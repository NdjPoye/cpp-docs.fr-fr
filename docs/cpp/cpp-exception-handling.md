---
title: Gestion des exceptions C++ | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling
- Visual C++, exception handling
ms.assetid: 65f80b44-9d0f-4d17-b910-07205a5c5c40
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9e23f99ad4c2b2a1129fa318fe6960e1c08df21d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="c-exception-handling"></a>Gestion d'exceptions C++
Le langage C++ fournit une prise en charge intégrée des levées et des interceptions d'exceptions. Lorsque vous programmez en C++, vous devez presque toujours utiliser la prise en charge intégrée des exceptions C++, comme décrit dans cette section.  
  
 Pour activer les exceptions C++ dans votre code, utilisez [/EHsc](../build/reference/eh-exception-handling-model.md).  
  
## <a name="in-this-section"></a>Dans cette section  
 Cette discussion sur la gestion des exceptions C++ comprend ce qui suit :  
  
-   [Try, catch et throw (instructions)](../cpp/try-throw-and-catch-statements-cpp.md)  
  
-   [L’évaluation des blocs Catch](../cpp/how-catch-blocks-are-evaluated-cpp.md)  
  
-   [Exceptions et déroulement de pile](../cpp/exceptions-and-stack-unwinding-in-cpp.md)  
  
-   [Spécifications d’exceptions](../cpp/exception-specifications-throw-cpp.md)  
  
-   [noexcept](../cpp/noexcept-cpp.md)  
  
-   [Exceptions C++ non gérées](../cpp/unhandled-cpp-exceptions.md)  
  
-   [Mélange d’exceptions C (structurées) et d’exceptions C++](../cpp/mixing-c-structured-and-cpp-exceptions.md)  
  
## <a name="support-for-earlier-mfc-exceptions"></a>Prise en charge des anciennes exceptions MFC  
 Depuis la version 4.0, MFC utilise le mécanisme de gestion des exceptions C++. Bien qu'il soit conseillé d'utiliser la gestion des exceptions C++ dans votre nouveau code, MFC 4.0 et les versions ultérieures ont conservé les macros des versions antérieures, de sorte que l'ancien code soit toujours valable. Les macros et le nouveau mécanisme peuvent également être combinés. Pour plus d’informations sur les mélanges de macros et gestion des exceptions C++ et sur la conversion d’ancien code pour utiliser le nouveau mécanisme, consultez les articles [Exceptions : utilisation des Macros MFC et des Exceptions C++](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) et [Exceptions : conversion à partir de MFC Macros d’exception](../mfc/exceptions-converting-from-mfc-exception-macros.md). Les anciennes macros d'exceptions MFC, si vous les utilisez toujours, correspondent aux mots clés d'exception C++. Consultez [Exceptions : modifications apportées aux Macros d’Exception de la Version 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion des exceptions](../cpp/exception-handling-in-visual-cpp.md)
