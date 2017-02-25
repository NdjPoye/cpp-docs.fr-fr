---
title: "ComPtrRef, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::Details::ComPtrRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ComPtrRef (classe)"
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ComPtrRef, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template <  
   typename T  
>  
class ComPtrRef : public ComPtrRefBase<T>;  
```  
  
#### Paramètres  
 `T`  
 Un type [CoomPtr\<T\>](../windows/comptr-class.md) ou un type dérivé de celui\-ci, pas seulement l'interface représentée par le ComPtr.  
  
## Notes  
 Représente une référence vers un objet de type ComPtr\<T\>.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[ComPtrRef::ComPtrRef, constructeur](../windows/comptrref-comptrref-constructor.md)|Initialise une nouvelle instance de la classe ComPtrRef à partir du pointeur vers un autre objet ComPtrRef spécifié.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[ComPtrRef::GetAddressOf, méthode](../windows/comptrref-getaddressof-method.md)|Récupère l'adresse d'un pointeur vers l'interface représentée par l'objet ComPtrRef objet.|  
|[ComPtrRef::ReleaseAndGetAddressOf, méthode](../windows/comptrref-releaseandgetaddressof-method.md)|Supprime l'objet ComPtrRef actuel et retourne un pointeur\-vers\-un\-pointeur vers l'interface représentée par l'objet ComPtrRef.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[ComPtrRef::operator InterfaceType\*\*, opérateur](../windows/comptrref-operator-interfacetype-star-star-operator.md)|Supprime l'objet ComPtrRef actuel et retourne un pointeur\-vers\-un\-pointeur vers l'interface représentée par l'objet ComPtrRef.|  
|[ComPtrRef::operator T\*, opérateur](../windows/comptrref-operator-t-star-operator.md)|Retourne la valeur de la donnée membre [ptr\_](../windows/comptrrefbase-ptr-data-member.md) de l'objet ComPtrRef actuel.|  
|[ComPtrRef::operator void\*\*, opérateur](../windows/comptrref-operator-void-star-star-operator.md)|Supprime l'objet ComPtrRef actuel, caste le pointeur vers l'interface représentée par l'objet ComPtrRef comme un pointeur\-vers\-pointeur\-vers `void`, puis retourne le pointeur de cast.|  
|[ComPtrRef::operator\*, opérateur](../windows/comptrref-operator-star-operator.md)|Récupère le pointeur vers l'interface représentée par l'objet ComPtrRef actuel.|  
|[ComPtrRef::operator\=\=, opérateur](../windows/comptrref-operator-equality-operator.md)|Indique si deux objets ComPtrRef sont égaux.|  
|[ComPtrRef::operator\!\=, opérateur](../windows/comptrref-operator-inequality-operator.md)|Indique si deux objets ComPtrRef ne sont pas égaux.|  
  
## Hiérarchie d'héritage  
 `ComPtrRefBase`  
  
 `ComPtrRef`  
  
## Configuration requise  
 **En\-tête :** client.h  
  
 **Espace de noms :** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)