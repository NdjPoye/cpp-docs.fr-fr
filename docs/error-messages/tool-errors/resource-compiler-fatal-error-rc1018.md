---
title: "Erreur irrécupérable RC1018 du compilateur de ressources | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC1018
dev_langs: C++
helpviewer_keywords: RC1018
ms.assetid: bb1d2efd-6898-412f-bb03-9ff94c54e4dc
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 44d67fcebfcafc2e7e9dcca53b9c6235f491784e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="resource-compiler-fatal-error-rc1018"></a>Erreur irrécupérable RC1018 du compilateur de ressources 
'#elif' inattendu  
  
 Le `#elif` directive ne figure pas dans un `#if`, **#ifdef**, ou **#ifndef** construire.  
  
 Assurez-vous qu’il existe un `#if`, **#ifdef**, ou **#ifndef** instruction en vigueur avant cette instruction.