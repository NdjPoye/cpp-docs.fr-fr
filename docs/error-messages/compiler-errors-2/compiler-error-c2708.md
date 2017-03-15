---
title: "Erreur du compilateur C2708 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2708"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2708"
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2708
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : la longueur en octets des paramètres diffère de celle de la référence ou de l'appel précédent  
  
 Une fonction [\_\_stdcall](../../cpp/stdcall.md) doit être précédée d'un prototype.  Sinon, le compilateur interprète le premier appel à la fonction comme un prototype et, s'il trouve un appel qui ne correspond pas, génère une erreur.  
  
 Pour résoudre ce problème, ajoutez un prototype de fonction.