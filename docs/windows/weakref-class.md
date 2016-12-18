---
title: "WeakRef, classe | Microsoft Docs"
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
  - "client/Microsoft::WRL::WeakRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WeakRef (classe)"
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WeakRef, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente une *référence faible* qui peut être utilisée uniquement par le Windows Runtime, pas par le COM classique. Une référence faible représente un objet qui peut être accessible ou non.  
  
## Syntaxe  
  
```  
class WeakRef : public ComPtr<IWeakReference>  
```  
  
## Notes  
 Un objet WeakRef conserve une *référence forte*, qui est associée à un objet, et peut être valide ou non valide. Appelez la méthode As\(\) ou AsIID\(\) pour obtenir une référence forte. Lorsque la référence forte est valide, elle peut accéder à l’objet associé. Lorsque la référence forte n’est pas valide \(`nullptr`\), l’objet associé n’est pas accessible.  
  
 Un objet WeakRef représente généralement un objet dont l’existence est contrôlée par une application ou un thread externe. Par exemple, construisez un objet WeakRef à partir d’une référence à un objet fichier. Pendant que le fichier est ouvert, la référence forte est valide, mais si le fichier est fermé, la référence forte devient non valide.  
  
 Notez qu’il existe un changement de comportement des méthodes [As](../windows/weakref-as-method.md), [AsIID](../windows/weakref-asiid-method.md) et [CopyTo](../windows/weakref-copyto-method.md) dans le Kit de développement logiciel SDK Windows 10. Auparavant, après avoir appelé l’une de ces méthodes, vous pouviez vérifier si le WeakRef était `nullptr` pour déterminer si une référence forte était obtenue avec succès, comme dans le code suivant :  
  
```cpp  
WeakRef wr; strongComptrRef.AsWeak(&wr); // Now suppose that the object strongComPtrRef points to no longer exists // and the following code tries to get a strong ref from the weak ref: ComPtr<ISomeInterface> strongRef; HRESULT hr = wr.As(&strongRef); // This check won't work with the Windows 10 SDK version of the library. // Use the HRESULT from previous As() call instead. if(wr == nullptr) { wprintf(L"Couldn’t get strong ref!"); }  
  
```  
  
 Le code ci\-dessus ne fonctionne pas lorsque vous utilisez le Kit de développement logiciel SDK Windows 10 \(ou version ultérieure\). Au lieu de cela, vérifiez le HRESULT retourné par la méthode As ou AsIID, ou vérifiez si le pointeur transmis est `nullptr`.  
  
```cpp  
if (hr != S_OK) { wprintf(L"Couldn't get strong ref!"); }  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[WeakRef::WeakRef, constructeur](../windows/weakref-weakref-constructor.md)|Initialise une nouvelle instance de la classe WeakRef.|  
|[WeakRef::~WeakRef, destructeur](../windows/weakref-tilde-weakref-destructor.md)|Désinitialise l’instance actuelle de la classe WeakRef.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[WeakRef::As, méthode](../windows/weakref-as-method.md)|Définit le paramètre de pointeur ComPtr spécifié pour qu’il représente l’interface spécifiée.|  
|[WeakRef::AsIID, méthode](../windows/weakref-asiid-method.md)|Définit le paramètre de pointeur ComPtr spécifié pour qu’il représente l’ID d’interface spécifié.|  
|[WeakRef::CopyTo, méthode](../windows/weakref-copyto-method.md)|Assigne un pointeur vers une interface, si disponible, à la variable pointeur spécifiée.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[WeakRef::operator&, opérateur](../windows/weakref-operator-ampersand-operator.md)|Retourne un objet ComPtrRef qui représente l’objet WeakRef actif.|  
  
## Hiérarchie d'héritage  
 `ComPtr`  
  
 `WeakRef`  
  
## Configuration requise  
 **En\-tête :** client.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)