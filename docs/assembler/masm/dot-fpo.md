---
title: . FPO | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .FPO
dev_langs: C++
helpviewer_keywords: .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 61d9209b5cf817d89e9e017626222a9cc73e209e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fpo"></a>.FPO
La barre d’outils. La directive de FPO contrôle l’émission d’enregistrements de débogage à la section ou du segment de .debug$ F.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
FPO (  
cdwLocals  
,   
cdwParams  
,   
cbProlog  
,   
cbRegs  
,   
fUseBP  
,   
cbFrame  
)  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `cdwLocals`  
 Nombre de variables locales, une valeur non signée 32 bits.  
  
 `cdwParams`  
 Taille des paramètres dans les valeurs de type DWORD, une valeur non signé 16 bits.  
  
 *cbProlog*  
 Nombre d’octets dans le code de prologue de fonction, une valeur non signé 8 bits.  
  
 `cbRegs`  
 Registres enregistrés des numéros.  
  
 `fUseBP`  
 Indique si le registre EBP a été alloué. 0 ou 1.  
  
 *cbFrame*  
 Indique le type de frame.  Consultez [FPO_DATA](http://msdn.microsoft.com/library/windows/desktop/ms679352) pour plus d’informations.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les directives](../../assembler/masm/directives-reference.md)