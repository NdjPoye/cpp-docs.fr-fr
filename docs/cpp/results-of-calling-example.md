---
title: "Résultats de l’exemple d’appel | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eaa47af17e46f51ef92cc15b8d2275b2ed8e05f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="results-of-calling-example"></a>Exemple de résultats de l'appel
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
  
## <a name="cdecl"></a>__cdecl  
 Le nom de fonction décoré C est « _MyFunc ».  
  
 ![Convention d’appel CDECL](../cpp/media/vc37i01.gif "vc37I01")  
Convention d’appel __cdecl  
  
## <a name="stdcall-and-thiscall"></a>__stdcall et thiscall  
 Le nom décoré C (`__stdcall`) est «_MyFunc@20. » Le nom décoré C++ est propriétaire.  
  
 ![&#95; &#95; stdcall et conventions d’appel thiscall](../cpp/media/vc37i02.gif "vc37I02")  
Conventions d’appel __stdcall et thiscall  
  
## <a name="fastcall"></a>__fastcall  
 Le nom décoré C (`__fastcall`) est «@MyFunc@20. » Le nom décoré C++ est propriétaire.  
  
 ![Convention d’appel pour &#95; &#95; fastcall](../cpp/media/vc37i03.gif "vc37I03")  
Convention d’appel __fastcall  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple d’appel : prototype et appel de fonction](../cpp/calling-example-function-prototype-and-call.md)