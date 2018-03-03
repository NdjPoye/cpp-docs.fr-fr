---
title: Erreur du compilateur C2218 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2218
dev_langs:
- C++
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cce36d9e8d4e8f2ac82ddec9a967ac7e045b4a03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2218"></a>Erreur du compilateur C2218
'__vectorcall' ne peut pas s'utiliser avec '/arch:IA32'  
  
 La convention d'appel `__vectorcall` est prise en charge uniquement dans le code natif sur les processeurs x86 et x64 qui incluent les extensions Streaming SIMD 2 (SSE2) et versions ultérieures. Pour plus d’informations, consultez [__vectorcall](../../cpp/vectorcall.md).  
  
 Pour corriger cette erreur, modifiez les options du compilateur pour cibler les jeux d'instructions SSE2, AVX ou AVX2. Pour plus d’informations, consultez l’article [/arch (x86)](../../build/reference/arch-x86.md).