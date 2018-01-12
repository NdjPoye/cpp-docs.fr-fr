---
title: "Erreur LNK1309 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1309
dev_langs: C++
helpviewer_keywords: LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 425fb564ae2bd099746fc9b76b496595caa10a0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1309"></a>Erreur des outils Éditeur de liens LNK1309
module type1 détecté ; non valide avec le commutateur/CLRIMAGETYPE : type2  
  
 Un type d’image CLR a été demandé avec **CLRIMAGETYPE** , mais l’éditeur de liens n’a pas pu produire une image de ce type, car un ou plusieurs modules sont incompatibles avec ce type.  
  
 Par exemple, l’erreur LNK1309 s’affiche si vous spécifiez **/CLRIMAGETYPE:safe** et que vous passez un module généré avec **/CLR : pure**.  
  
 Vous verrez également LNK1309 si vous essayez de générer une application pure CLR de confiance partiel à l’aide de ptrustu [d] .lib. Pour plus d’informations sur la création d’une application de confiance partielle, consultez [Comment : créer une Application partiellement approuvée en supprimant la dépendance sur la DLL de la bibliothèque CRT](../../dotnet/create-a-partially-trusted-application.md).  
  
 Pour plus d’informations, consultez [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md) et [/CLRIMAGETYPE (spécifier Type of CLR Image)](../../build/reference/clrimagetype-specify-type-of-clr-image.md).