---
title: "WeakReference::Resolve, m&#233;thode (espace de noms de plateforme) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/WeakReference::Resolve"
ms.assetid: 78bbcadd-89d0-4863-a4e8-1d84040eed7d
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WeakReference::Resolve, m&#233;thode (espace de noms de plateforme)
Retourne un handle vers la classe ref d'origine ou `nullptr` si l'objet n'existe plus.  
  
## Syntaxe  
  
```vb  
  
template<typename T>  
T^ Resolve() const  
```  
  
#### Paramètres  
  
## Valeur de propriété\/valeur de retour  
 Handle vers la classe ref à laquelle l'objet WeakReference était associé précédemment ou nullptr.  
  
## Notes  
  
## Exemple  
 Il s'agit de la description d'un exemple de code.  
  
```  
  
Bar^ bar = ref new Bar(); //use bar... if (bar != nullptr) { WeakReference wr(bar); Bar^ newReference = wr.Resolve<Bar>(); }  
```  
  
 Notez que le paramètre de type est T au lieu de T^.  
  
## Voir aussi  
 [Espace de noms de plateforme](../cppcx/platform-namespace-c-cx.md)