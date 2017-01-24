---
title: "CObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes de base, objets MFC"
  - "CObject class"
  - "object classes"
  - "objets (C++), base class for MFC"
ms.assetid: 95e9acd3-d9eb-4ac0-b52b-ca4a501a7a3a
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe de base principale de la bibliothèque MFC.  
  
## Syntaxe  
  
```  
class AFX_NOVTABLE CObject  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CObject::CObject](../Topic/CObject::CObject.md)|Constructeur par défaut.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CObject::AssertValid](../Topic/CObject::AssertValid.md)|Valide l'état de cet objet.|  
|[CObject::Dump](../Topic/CObject::Dump.md)|Produit un dump de diagnostic de cet objet.|  
|[CObject::GetRuntimeClass](../Topic/CObject::GetRuntimeClass.md)|Retourne la structure d' `CRuntimeClass` correspondant à cette classe d'objet.|  
|[CObject::IsKindOf](../Topic/CObject::IsKindOf.md)|Teste la relation de cet objet à une classe donnée.|  
|[CObject::IsSerializable](../Topic/CObject::IsSerializable.md)|Tests pour voir si cet objet peut être sérialisé.|  
|[CObject::Serialize](../Topic/CObject::Serialize.md)|Chargement ou stocke un objet de\/à une archive.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CObject::operator delete](../Topic/CObject::operator%20delete.md)|Opérateur de **supprimer** de special.|  
|[CObject::operator new](../Topic/CObject::operator%20new.md)|Opérateur de **nouveau** de special.|  
  
## Notes  
 Elle sert racine non seulement pour les classes de la bibliothèque par exemple `CFile` et `CObList`, mais également des classes que vous écrivez.  `CObject` fournit des services de base, notamment  
  
-   Prise en charge de la sérialisation  
  
-   Les informations sur la classe d'exécution  
  
-   Sortie de diagnostic d'objet  
  
-   Compatibilité avec les classes de collection  
  
 Notez qu' `CObject` ne prend pas en charge l'héritage multiple.  Les classes dérivées peuvent avoir qu'une seule classe de base d' `CObject` , et c' `CObject` doit être situé le plus à gauche dans la hiérarchie.  Il est autorisé, toutefois, pour que les structures et l'`CObject`non \- les classes dérivées dans les branches droits d'héritage multiple.  
  
 Vous réaliserez des principaux avantages de dériver de `CObject` si vous utilisez certaines macros facultatives dans votre implémentation de classe et déclarations.  
  
 Les macros de premier niveau, le [DECLARE\_DYNAMIC](../Topic/DECLARE_DYNAMIC.md) et l' [IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md), l'accès à l'exécution de null au nom de classe et son emplacement dans la hiérarchie.  Cela, ensuite, permet de faire un dump de diagnostic explicite.  
  
 Les macros de deuxième niveau, [DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md) et [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md), incluent toutes les fonctionnalités des macros de premier niveau, et elles permettent à un objet d'être « sérialisé » depuis et vers une « archive. »  
  
 Pour plus d'informations sur dériver des classes MFC \(Microsoft Foundation et des classes C\+\+ en général et utiliser `CObject`, consultez [À l'aide de CObject](../../mfc/using-cobject.md) et le [sérialisation](../../mfc/serialization-in-mfc.md).  
  
## Hiérarchie d'héritage  
 `CObject`  
  
## Configuration requise  
 **Header:** afx.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)