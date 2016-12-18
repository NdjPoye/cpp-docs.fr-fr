---
title: "QueryInterface | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "QueryInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interfaces, disponibilité"
  - "interfaces, pointeurs"
  - "QueryInterface (méthode)"
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# QueryInterface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bien qu'il y ait des mécanismes par lesquels un objet peut exprimer la fonctionnalité il fournisse statiquement \(avant qu'il est instancié\), le mécanisme COM de concept fondamental est d'utiliser la méthode d' **IUnknown** appelée [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521).  
  
 Chaque interface est dérivée d' **IUnknown**, pour chaque interface a une implémentation d' `QueryInterface`.  Indépendamment de l'implémentation, cette méthode recherche un objet à l'aide de l'IID de l'interface à laquelle l'appelant veut un pointeur.  Si les prend en charge l'objet d'interface qui, `QueryInterface` extrait un pointeur vers l'interface, tout en également appelant `AddRef`.  Sinon, il retourne un code d'erreur d' **E\_NOINTERFACE** .  
  
 Notez que vous devez vous conformer aux règles de [décompte de références](../atl/reference-counting.md) à tout moment.  Si vous appelez **Release** sur un pointeur d'interface pour décrémenter le décompte de références à zéro, vous ne devez pas utiliser ce pointeur de nouveau.  Occasionnellement vous devrez peut\-être obtenir une référence faible à un objet \(autrement dit, vous pouvez souhaiter obtenir un pointeur vers une de ses interfaces sans incrémenter le décompte de références\), mais il n'est pas acceptable d'effectuer cette opération en appelant `QueryInterface` suivi de **Release**.  Le pointeur obtenu de cette façon n'est pas valide et ne doit pas être utilisé.  Elle devient plus facilement affiche lorsque [\_ATL\_DEBUG\_INTERFACES](../Topic/_ATL_DEBUG_INTERFACES.md) est défini, donc définir cette macro est un moyen d'identifier les bogues de décompte de références.  
  
## Voir aussi  
 [Introduction to COM](../atl/introduction-to-com.md)   
 [QueryInterface: Navigating in an Object](http://msdn.microsoft.com/library/windows/desktop/ms687230)