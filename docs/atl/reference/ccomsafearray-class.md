---
title: "CComSafeArray, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComSafeArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComSafeArray, classe"
ms.assetid: ee349aef-33db-4c85-bd08-5d86a3c9d53a
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CComSafeArray, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est un wrapper pour la structure **SAFEARRAY**.  
  
## Syntaxe  
  
```  
template <  
   typename T,  
   VARTYPE _vartype = _ATL_AutomationType< T >::type  
>  
class CComSafeArray  
```  
  
#### Paramètres  
 `T`  
 Type de données à stocker dans le tableau.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComSafeArray::CComSafeArray](../Topic/CComSafeArray::CComSafeArray.md)|Constructeur.|  
|[CComSafeArray::~CComSafeArray](../Topic/CComSafeArray::~CComSafeArray.md)|Destructeur.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComSafeArray::Add](../Topic/CComSafeArray::Add.md)|Ajoute un ou plusieurs éléments ou une structure **SAFEARRAY** à un objet `CComSafeArray`.|  
|[CComSafeArray::Attach](../Topic/CComSafeArray::Attach.md)|Attache une structure **SAFEARRAY** à un objet `CComSafeArray`.|  
|[CComSafeArray::CopyFrom](../Topic/CComSafeArray::CopyFrom.md)|Copie le contenu d’une structure **SAFEARRAY** dans l’objet `CComSafeArray`.|  
|[CComSafeArray::CopyTo](../Topic/CComSafeArray::CopyTo.md)|Crée une copie de l’objet `CComSafeArray`.|  
|[CComSafeArray::Create](../Topic/CComSafeArray::Create.md)|Crée un objet `CComSafeArray`.|  
|[CComSafeArray::Destroy](../Topic/CComSafeArray::Destroy.md)|Détruit un objet `CComSafeArray`.|  
|[CComSafeArray::Detach](../Topic/CComSafeArray::Detach.md)|Détache une structure **SAFEARRAY** d’un objet `CComSafeArray`.|  
|[CComSafeArray::GetAt](../Topic/CComSafeArray::GetAt.md)|Récupère un élément unique à partir d’un tableau unidimensionnel.|  
|[CComSafeArray::GetCount](../Topic/CComSafeArray::GetCount.md)|Retourne le nombre d'éléments du tableau.|  
|[CComSafeArray::GetDimensions](../Topic/CComSafeArray::GetDimensions.md)|Retourne le nombre de dimensions du tableau.|  
|[CComSafeArray::GetLowerBound](../Topic/CComSafeArray::GetLowerBound.md)|Retourne la limite inférieure d’une dimension donnée du tableau.|  
|[CComSafeArray::GetSafeArrayPtr](../Topic/CComSafeArray::GetSafeArrayPtr.md)|Retourne l’adresse du membre de données `m_psa`.|  
|[CComSafeArray::GetType](../Topic/CComSafeArray::GetType.md)|Retourne le type de données stocké dans le tableau.|  
|[CComSafeArray::GetUpperBound](../Topic/CComSafeArray::GetUpperBound.md)|Retourne la limite supérieure d’une dimension du tableau.|  
|[CComSafeArray::IsSizable](../Topic/CComSafeArray::IsSizable.md)|Teste si un objet `CComSafeArray` peut être redimensionné.|  
|[CComSafeArray::MultiDimGetAt](../Topic/CComSafeArray::MultiDimGetAt.md)|Récupère un élément unique à partir d’un tableau multidimensionnel.|  
|[CComSafeArray::MultiDimSetAt](../Topic/CComSafeArray::MultiDimSetAt.md)|Définit la valeur d’un élément d’un tableau multidimensionnel.|  
|[CComSafeArray::Resize](../Topic/CComSafeArray::Resize.md)|Redimensionne un objet `CComSafeArray`.|  
|[CComSafeArray::SetAt](../Topic/CComSafeArray::SetAt.md)|Définit la valeur d’un élément d’un tableau unidimensionnel.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComSafeArray::operator LPSAFEARRAY](../Topic/CComSafeArray::operator%20LPSAFEARRAY.md)|Effectue une conversion de type \(transtypage\) d’une valeur en pointeur **SAFEARRAY**.|  
|[CComSafeArray::operator](../Topic/CComSafeArray::operator.md)|Récupère un élément du tableau.|  
|[CComSafeArray::operator \=](../Topic/CComSafeArray::operator%20=.md)|Opérateur d'assignation.|  
  
### Membres de données publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComSafeArray::m\_psa](../Topic/CComSafeArray::m_psa.md)|Ce membre de données conserve l’adresse de la structure **SAFEARRAY**.|  
  
## Notes  
 `CComSafeArray` fournit un wrapper pour la classe [SAFEARRAY Data Type](http://msdn.microsoft.com/fr-fr/9ec8025b-4763-4526-ab45-390c5d8b3b1e), ce qui simplifie la création et la gestion des tableaux unidimensionnels et multidimensionnels de pratiquement n’importe quel type prenant en charge VARIANT.  
  
 `CComSafeArray` simplifie le transmission de tableaux entre processus et offre en outre une sécurité renforcée en vérifiant les valeurs d’index de tableau par rapport aux limites inférieure et supérieure.  
  
 La limite inférieure d’un `CComSafeArray` peut commencer à n’importe quelle valeur définie par l’utilisateur ; cependant, les tableaux accessibles via C\+\+ doivent utiliser une limite inférieure de 0. D’autres langages comme Visual Basic peuvent utiliser d’autres valeurs de délimitation \(par exemple, de \-10 à 10\).  
  
 Utilisez [CComSafeArray::Create](../Topic/CComSafeArray::Create.md) pour créer un objet `CComSafeArray` et [CComSafeArray::Destroy](../Topic/CComSafeArray::Destroy.md) pour le supprimer.  
  
 Un `CComSafeArray` peut contenir le sous\-ensemble de types de données VARIANT suivant :  
  
|VARTYPE|Description|  
|-------------|-----------------|  
|VT\_I1|char|  
|VT\_I2|short|  
|VT\_I4|int|  
|VT\_I4|long|  
|VT\_I8|longlong|  
|VT\_UI1|byte|  
|VT\_UI2|ushort|  
|VT\_UI4|uint|  
|VT\_UI4|ulong|  
|VT\_UI8|ulonglong|  
|VT\_R4|float|  
|VT\_R8|double|  
|VT\_DECIMAL|pointeur décimal|  
|VT\_VARIANT|pointeur de type Variant|  
|VT\_CY|Currency \(type de données\)|  
  
## Configuration requise  
 **En\-tête :** atlsafe.h  
  
## Exemple  
 [!code-cpp[NVC_ATL_Utilities#75](../../atl/codesnippet/CPP/ccomsafearray-class_1.cpp)]  
  
## Voir aussi  
 [SAFEARRAY Data Type](http://msdn.microsoft.com/fr-fr/9ec8025b-4763-4526-ab45-390c5d8b3b1e)   
 [CComSafeArray::Create](../Topic/CComSafeArray::Create.md)   
 [CComSafeArray::Destroy](../Topic/CComSafeArray::Destroy.md)   
 [Class Overview](../../atl/atl-class-overview.md)