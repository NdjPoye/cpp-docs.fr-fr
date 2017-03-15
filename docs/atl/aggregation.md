---
title: "Aggregation | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregate objects [C++]"
  - "aggregation [C++]"
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Aggregation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il arrive lorsque l'implémenteur d'un objet souhaite tirer parti des services offerts par un autre objet, prégénéré.  De plus, il souhaite que ce deuxième objet s'affiche en tant que partie naturelle de la première.  COM atteint ces deux objectifs via la relation contenant\-contenu et le regroupement.  
  
 Le regroupement signifie que l'objet externe \(\) qui crée l'objet \(interne\) contenu dans le cadre de le processus de création et interfaces de l'objet interne sont exposées par l'externe.  Un objet vous permet d'être pouvant être regroupé en agrégats ou pas.  Si c'est le cas, il doit respecter certaines règles pour le regroupement fonctionne correctement.  
  
 Essentiellement, tous les appels de méthode d' **IUnknown** sur l'objet contenu doivent les déléguer à l'objet contenant.  
  
## Voir aussi  
 [Introduction to COM](../atl/introduction-to-com.md)   
 [Reusing Objects](http://msdn.microsoft.com/library/windows/desktop/ms678443)