---
title: "LNK4086 d’avertissement des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4086
dev_langs: C++
helpviewer_keywords: LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fcd701401c798d7126be4f4239ee533b14d90652
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4086"></a>Avertissement des outils Éditeur de liens LNK4086
point d’entrée 'fonction' n’est pas __stdcall avec des octets de 'nombre' arguments ; image ne peut pas s’exécuter  
  
 Le point d’entrée pour une DLL doit être `__stdcall`. Vous pouvez soit recompiler la fonction avec le [GZ](../../build/reference/gd-gr-gv-gz-calling-convention.md) soit spécifier `__stdcall` ou WINAPI lors de la définition de la fonction.