---
title: "Exemple de r&#233;sultats de l&#39;appel | Microsoft Docs"
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
  - "exemples (C++), résultats de l'appel"
  - "résultats, __cdecl (appel)"
  - "résultats, __fastcall (appel)"
  - "résultats, __stdcall (appel)"
  - "résultats, thiscall (appel)"
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Exemple de r&#233;sultats de l&#39;appel
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
  
## \_\_cdecl  
 Le nom de fonction décoré C est « \_MyFunc ».  
  
 ![Convention d'appel CDECL](../cpp/media/vc37i01.png "vc37I01")  
Convention d'appel \_\_cdecl  
  
## \_\_stdcall et thiscall  
 Le nom décoré C \(`__stdcall`\) est « \_MyFunc@20 ». Le nom décoré C\+\+ est propriétaire.  
  
 ![Conventions d'appel &#95;&#95;stdcall et thiscall](../cpp/media/vc37i02.png "vc37I02")  
Conventions d'appel \_\_stdcall et thiscall  
  
## \_\_fastcall  
 Le nom décoré C \(`__fastcall`\) est « @MyFunc@20 ». Le nom décoré C\+\+ est propriétaire.  
  
 ![Convention d'appel de &#95;&#95;fastcall](../cpp/media/vc37i03.png "vc37I03")  
Convention d'appel \_\_fastcall  
  
### FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Exemple d'appel : prototype de fonction et appel](../cpp/calling-example-function-prototype-and-call.md)