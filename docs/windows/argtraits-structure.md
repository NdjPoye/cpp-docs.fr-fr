---
title: "ArgTraits, structure | Microsoft Docs"
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
  - "event/Microsoft::WRL::Details::ArgTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ArgTraits (structure)"
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ArgTraits, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template<  
   typename TMemberFunction  
>  
struct ArgTraits;  
template<  
   typename TDelegateInterface  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8,  
   typename TArg9  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;  
```  
  
#### Paramètres  
 `TMemberFunction`  
 Le paramètre Typename pour une structure ArgTraits ne pouvant correspondre à une signature de la méthode Invoke.  
  
 `TDelegateInterface`  
 Une interface de délégué.  
  
 `TArg1`  
 Le type du premier argument de la méthode Invoke.  
  
 `TArg2`  
 Le type du deuxième argument de la méthode Invoke.  
  
 `TArg3`  
 Le type du troisième argument de la méthode Invoke.  
  
 `TArg4`  
 Le type du quatrième argument de la méthode Invoke.  
  
 `TArg5`  
 Le type du cinquième argument de la méthode Invoke.  
  
 `TArg6`  
 Le type du sixième argument de la méthode Invoke.  
  
 `TArg7`  
 Le type du septième argument de la méthode Invoke.  
  
 `TArg8`  
 Le type du huitième argument de la méthode Invoke.  
  
 `TArg9`  
 Le type du neuvième argument de la méthode Invoke.  
  
## Notes  
 La structure `ArgTraits` déclare une interface de délégué spécifiée et une fonction membre anonyme possédant un nombre de paramètres spécifié.  
  
## Membres  
  
### Typedefs publics  
  
|Name|Description|  
|----------|-----------------|  
|`Arg1Type`|Le typedef de TArg1.|  
|`Arg2Type`|Le typedef de TArg2.|  
|`Arg3Type`|Le typedef de TArg3.|  
|`Arg4Type`|Le typedef de TArg4.|  
|`Arg5Type`|Le typedef de TArg5.|  
|`Arg6Type`|Le typedef de TArg6.|  
|`Arg7Type`|Le typedef de TArg7.|  
|`Arg8Type`|Le typedef de TArg8.|  
|`Arg9Type`|Le typedef de TArg9.|  
  
### Constantes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[ArgTraits::args, constante](../windows/argtraits-args-constant.md)|Conserve le nombre de paramètres de la méthode Invoke d'une interface de délégué.|  
  
## Hiérarchie d'héritage  
 `ArgTraits`  
  
## Configuration requise  
 **En\-tête:** event.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)