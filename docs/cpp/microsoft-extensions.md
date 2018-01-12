---
title: Extensions Microsoft | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: Microsoft extensions to C/C++
ms.assetid: 68654516-24ef-4f33-aae2-175f86cc1979
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ef1a0ea32e893551b7278a424f49520aa0537298
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
