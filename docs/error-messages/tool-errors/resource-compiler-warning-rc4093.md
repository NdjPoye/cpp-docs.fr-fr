---
title: Avertissement RC4093 du compilateur de ressources | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC4093
dev_langs:
- C++
helpviewer_keywords:
- RC4093
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d21cbba379e72675b8957be58dc712b83673947
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-warning-rc4093"></a>Avertissement RC4093 du compilateur de ressources 
saut de ligne sans séquence d’échappement dans une constante caractère du code inactif  
  
 L’expression constante d’un `#if`, `#elif`, **#ifdef**, ou **#ifndef** directive de préprocesseur à zéro, rendant le code qui suit inactif. Dans ce code inactif, un caractère de saut de ligne apparaît dans un jeu de guillemets simples ou doubles.  
  
 Tout le texte jusqu'à ce que le guillemet double suivant a été considérées comme étant dans une constante caractère.