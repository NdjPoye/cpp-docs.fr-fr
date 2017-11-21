---
title: "L’erreur C2696 erreur de compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2696
dev_langs: C++
helpviewer_keywords: C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 70ccaf34a0191f0bd69c95d2cb110f6e6542a6d1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2696"></a>Erreur C2696 erreur de compilateur
Impossible de créer un objet temporaire d’un type managé 'type'  
  
Des références aux `const` dans un programme non managé que le compilateur appelle le constructeur et créer un objet temporaire sur la pile. Toutefois, une classe managée ne peut jamais être créée sur la pile.  
  
L’erreur C2696 est uniquement accessible à l’aide de l’option du compilateur obsolète **oldSyntax ;**.  
