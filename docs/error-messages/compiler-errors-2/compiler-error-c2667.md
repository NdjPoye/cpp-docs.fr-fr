---
title: "Erreur du compilateur C2667 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2667"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2667"
ms.assetid: 3c91d9d1-18fa-4e0d-a9ba-984d38980ca3
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2667
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : aucune des 'nombre' surcharges ne dispose d'une meilleure conversion  
  
 Un appel de fonction surchargée est ambigu et ne peut pas être résolu.  
  
 La conversion nécessaire pour faire correspondre les paramètres réels dans l'appel de fonction à l'une des fonctions surchargées doit impérativement être meilleure que les conversions requises par toutes les autres fonctions surchargées.  
  
 Pour plus d'informations sur le classement partiel des modèles de fonction, consultez l'article Q240869 de la Base de connaissances.