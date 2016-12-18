---
title: "ComPtr, classe | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ComPtr (classe)"
ms.assetid: a6551902-6819-478a-8df7-b6f312ab1fb0
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Crée un type de *pointeur intelligent* représentant l'interface spécifiée par le paramètre de modèle. ComPtr met à jour automatiquement un décompte de références pour le pointeur d'interface sous\-jacent et libère l'interface quand le décompte de références atteint zéro.  
  
## Syntaxe  
  
```  
template <  
   typename T  
>  
class ComPtr;  
  
template<  
   class U  
>  
friend class ComPtr;  
```  
  
#### Paramètres  
 `T`  
 Interface représentée par ComPtr.  
  
 `U`  
 Classe dont le ComPtr actuel est proche. \(Le modèle qui utilise ce paramètre est protégé\).  
  
## Notes  
 ComPtr\<\> déclare un type qui représente le pointeur d’interface sous\-jacent. Utilisez ComPtr\<\> pour déclarer une variable, puis utilisez l’opérateur d’accès aux membres \(`->`\) pour accéder à une fonction membre d’interface.  
  
 Pour plus d’informations sur les pointeurs intelligents, consultez la sous\-section relative aux pointeurs intelligents COM dans la rubrique [COM Coding Practices](http://msdn.microsoft.com/fr-fr/76aca556-b4d6-4e67-a2a3-4439900f0c39) de MSDN Library.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`InterfaceType`|Synonyme du type spécifié par le paramètre de modèle `T`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[ComPtr::ComPtr, constructeur](../windows/comptr-comptr-constructor.md)|Initialise une nouvelle instance de la classe ComPtr. Les surcharges fournissent des constructeurs par défaut, de copie, de déplacement et de conversion.|  
|[ComPtr::~ComPtr, destructeur](../windows/comptr-tilde-comptr-destructor.md)|Annule l’initialisation d’une instance de ComPtr.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[ComPtr::As, méthode](../windows/comptr-as-method.md)|Retourne un objet ComPtr qui représente l’interface identifiée par le paramètre de modèle spécifié.|  
|[ComPtr::AsIID, méthode](../windows/comptr-asiid-method.md)|Retourne un objet ComPtr qui représente l’interface identifiée par l’ID d’interface spécifié.|  
|[ComPtr::AsWeak, méthode](../windows/comptr-asweak-method.md)|Récupère une référence faible à l’objet actif.|  
|[ComPtr::Attach, méthode](../windows/comptr-attach-method.md)|Associe ce ComPtr au type d’interface spécifié par le paramètre de type de modèle actuel.|  
|[ComPtr::CopyTo, méthode](../windows/comptr-copyto-method.md)|Copie l’interface actuelle ou spécifiée associée à ce ComPtr au pointeur de sortie spécifié.|  
|[ComPtr::Detach, méthode](../windows/comptr-detach-method.md)|Dissocie ce ComPtr de l’interface qu’il représente.|  
|[ComPtr::Get, méthode](../windows/comptr-get-method.md)|Récupère un pointeur vers l’interface associée à ce ComPtr.|  
|[ComPtr::GetAddressOf, méthode](../windows/comptr-getaddressof-method.md)|Récupère l’adresse du membre de données [ptr\_](../windows/comptr-ptr-data-member.md) qui contient un pointeur vers l’interface représentée par ce ComPtr.|  
|[ComPtr::ReleaseAndGetAddressOf, méthode](../windows/comptr-releaseandgetaddressof-method.md)|Libère l’interface associée à ce ComPtr, puis récupère l’adresse du membre de données [ptr\_](../windows/comptr-ptr-data-member.md), qui contient un pointeur vers l’interface libérée.|  
|[ComPtr::Reset](../windows/comptr-reset.md)|Libère toutes les références pour le pointeur vers l'interface qui est associée à ce ComPtr.|  
|[ComPtr::Swap, méthode](../windows/comptr-swap-method.md)|Échange l’interface gérée par le ComPtr actuel avec l’interface gérée par le ComPtr spécifié.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[ComPtr::InternalAddRef, méthode](../windows/comptr-internaladdref-method.md)|Incrémente le décompte des références de l’interface associée à ce ComPtr.|  
|[ComPtr::InternalRelease, méthode](../windows/comptr-internalrelease-method.md)|Effectue une opération de libération de COM sur l’interface associée à ce ComPtr.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[ComPtr::operator Microsoft::WRL::Details::BoolType, opérateur](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)|Indique si un ComPtr gère la durée de vie des objets d’une interface.|  
|[ComPtr::operator&, opérateur](../windows/comptr-operator-ampersand-operator.md)|Récupère l’adresse du ComPtr actuel.|  
|[ComPtr::operator\=, opérateur](../windows/comptr-operator-assign-operator.md)|Assigne une valeur au ComPtr actuel.|  
|[ComPtr::operator\-\>, opérateur](../windows/comptr-operator-arrow-operator.md)|Récupère un pointeur vers le type spécifié par le paramètre de modèle actuel.|  
|[ComPtr::operator\=\=, opérateur](../windows/comptr-operator-equality-operator.md)|Indique si deux objets ComPtr sont égaux.|  
|[ComPtr::operator\!\=, opérateur](../windows/comptr-operator-inequality-operator.md)|Indique si deux objets ComPtr ne sont pas égaux.|  
  
### Membres de données protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[ComPtr::ptr\_, données de membre](../windows/comptr-ptr-data-member.md)|Contient un pointeur vers l’interface associée à ce ComPtr, et gérée par ce dernier.|  
  
## Hiérarchie d'héritage  
 `ComPtr`  
  
## Configuration requise  
 **En\-tête :** client.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)