---
title: Erreur du compilateur C3908 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3908
dev_langs: C++
helpviewer_keywords: C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e3c364709704e5051bcfcb77777d15b18d46b375
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3908"></a>Erreur du compilateur C3908
niveau d’accès moins restrictif que celui de 'construction'  
  
 Une méthode d’accesseur de propriété (get ou set) ne peut pas avoir d’accès moins restrictif que l’accès spécifié pour la propriété proprement dite.  De même, pour les méthodes d’accesseur événement.  
  
 Pour plus d’informations, consultez [propriété](../../windows/property-cpp-component-extensions.md) et [événement](../../windows/event-cpp-component-extensions.md).  
  
 L’exemple suivant génère l’erreur C3908 :  
  
```  
// C3908.cpp  
// compile with: /clr  
ref class X {  
protected:  
   property int i {  
   public:   // C3908 property i is protected   
      int get();  
   private:  
      void set(int);   // OK more restrictive  
   };  
};  
```