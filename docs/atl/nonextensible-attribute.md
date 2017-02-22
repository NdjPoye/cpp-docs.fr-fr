---
title: "nonextensible Attribute | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "nonextensible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interfaces doubles, nonextensible attribute"
  - "nonextensible attribute"
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# nonextensible Attribute
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si une interface double n'est pas étendue au moment de l'exécution \(autrement dit, vous fournirez ne pas les méthodes ou les propriétés via **IDispatch::Invoke** qui ne sont pas disponibles via le pointeur vtable\), vous devez appliquer l'attribut de **nonextensible** à votre définition d'interface.  Cet attribut fournit des informations aux langages clients \(tels que Visual Basic\) qui peuvent être utilisés pour activer la vérification complète de code au moment de la compilation.  Si cet attribut n'est pas fourni, les bogues peuvent rester masqués dans le code client jusqu ' à le moment de l'exécution.  
  
 Pour plus d'informations sur l'attribut de **nonextensible** et un exemple, consultez [non extensible](../windows/nonextensible.md).  
  
## Voir aussi  
 [Dual Interfaces and ATL](../atl/dual-interfaces-and-atl.md)