---
title: "Avertissement des outils &#201;diteur de liens LNK4086 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4086"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4086"
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement des outils &#201;diteur de liens LNK4086
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la 'fonction' de point d'entrée n'est pas \_\_stdcall avec des arguments de 'nombre' octets ; l'image risque de ne pas s'exécuter  
  
 Le point d'entrée d'une DLL doit être `__stdcall`.  Vous pouvez soit recompiler la fonction avec l'option [\/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md), soit spécifier `__stdcall` ou WINAPI lors de la définition de la fonction.