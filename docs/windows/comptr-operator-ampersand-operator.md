---
title: "ComPtr::operator&amp; opérateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::operator&
dev_langs: C++
helpviewer_keywords: operator& operator
ms.assetid: 2d77fda6-f4b2-45c1-8a0e-fbc355013531
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2b464a77fedf0d996210040b744faea0ee7372ef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="comptroperatoramp-operator"></a>ComPtr::operator&amp; (opérateur)
Libère l’interface associée à ce `ComPtr` de l’objet, puis récupère l’adresse de le `ComPtr` objet.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&()  
  
const Details::ComPtrRef<const WeakRef> operator&() const  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Une référence faible à actuel `ComPtr`.  
  
## <a name="remarks"></a>Remarques  
 Cette méthode diffère [ComPtr::GetAddressOf](../windows/comptr-getaddressof-method.md) dans la mesure où cette méthode libère une référence au pointeur d’interface. Utilisez `ComPtr::GetAddressOf` quand vous exigent l’adresse du pointeur d’interface, mais ne souhaitez pas libérer cette interface.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** client.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [ComPtr, classe](../windows/comptr-class.md)