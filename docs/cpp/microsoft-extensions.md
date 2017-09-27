---
title: Extensions Microsoft | Documents Microsoft
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
- Microsoft extensions to C/C++
ms.assetid: 68654516-24ef-4f33-aae2-175f86cc1979
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9de205df0ff566c2638d09c627534bb8327de4f2
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="microsoft-extensions"></a>Extensions Microsoft
*l’instruction asm*:  
 **__asm***assembly-instruction* **;** s’abonner    
  
 **__asm {***assembly-instruction-list***} ;** s’abonner      
  
 *assembly-instruction-list*:  
 *assembly-instruction* **;** s’abonner  
  
 *assembly-instruction* **;** *assembly-instruction-list* **;** s’abonner  
  
 *MS-modifier-list*:  
 *MS-modifier ms-modifier-list*opt  
  
 *MS-modifier*:  
 **__cdecl**  
  
 **__fastcall**  
  
 **__stdcall**  
  
 **__syscall** (réservé pour les implémentations futures)  
  
 **__oldcall** (réservé pour les implémentations futures)  
  
 **__unaligned** (réservé pour les implémentations futures)  
  
 *modificateur de base*  
  
 *modificateur en fonction*:  
 **__based (** *en fonction de type* **)**  
  
 *en fonction de type*:  
 *name*  

