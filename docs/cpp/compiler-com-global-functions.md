---
title: Les fonctions globales COM du compilateur | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 74449d26-50a2-47c7-b175-7cf2cf83533e
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: be73622037c1c058edffa681ccd79322b8252633
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-com-global-functions"></a>Fonctions globales COM du compilateur
**Section spécifique à Microsoft**  
  
 Les routines suivantes sont disponibles :  
  
|Fonction|Description|  
|--------------|-----------------|  
|[_com_raise_error](../cpp/com-raise-error.md)|Lève un [_com_error](../cpp/com-error-class.md) en réponse à un échec.|  
|[_set_com_error_handler](../cpp/set-com-error-handler.md)|Remplace la fonction par défaut utilisée pour la gestion des erreurs COM.|  
|[ConvertBSTRToString](../cpp/convertbstrtostring.md)|Convertit un `BSTR` valeur un **char \*** .|  
|[ConvertStringToBSTR](../cpp/convertstringtobstr.md)|Convertit un **char \***  la valeur en un `BSTR`.|  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Classes de prise en charge COM du compilateur](../cpp/compiler-com-support-classes.md)   
 [Prise en charge COM du compilateur](../cpp/compiler-com-support.md)