---
title: "Avertissement du compilateur (niveau 1) C4711 | Microsoft Docs"
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
  - "C4711"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4711"
ms.assetid: 270506ab-fead-4328-b714-2978113be238
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4711
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fonction 'fonction' sélectionnée pour expansion inline  
  
 Le compilateur applique la fonctionnalité inline à la fonction donnée, bien que celle\-ci n'a pas été marquée pour inline.  
  
 C4711 est activé si [\/Ob2](../../build/reference/ob-inline-function-expansion.md) est spécifié.  
  
 La fonctionnalité inline est appliquée à la discrétion du compilateur.  Cet avertissement est informatif.  
  
 Cet avertissement est désactivé par défaut.  Pour activer un avertissement, utilisez [\#pragma warning](../../preprocessor/warning.md).  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).