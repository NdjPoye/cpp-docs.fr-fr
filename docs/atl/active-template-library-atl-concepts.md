---
title: "Concepts ATL (Active Template Library) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, à propos d'ATL"
ms.assetid: a3960991-4d76-4da5-9568-3fa7fde53ff4
caps.latest.revision: 18
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Concepts ATL (Active Template Library)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque ATL \(ATL\) est un ensemble de classes basée sur les formulaires C\+\+ qui vous permettent de créer des petits, rapides objets de \(COM\) \(component object model\).  Elle possède une prise en charge spéciale les principales fonctionnalités de COM, y compris les implémentations de cotations boursières, les interfaces doubles, les interfaces standard d'énumérateur COM, des points de connexion, des interfaces volantes, et des contrôles ActiveX.  
  
 Si vous avez de nombreux ATL programmation, vous voudrez savoir plus sur les attributs, une nouvelle fonctionnalité dans Visual C\+\+ .NET qui est conçue pour simplifier la programmation COM.  Pour plus d'informations, consultez [programmation par attributs](../windows/attributed-programming-concepts.md).  
  
## Dans cette section  
 [Didacticiel ATL](../atl/active-template-library-atl-tutorial.md)  
 Vous assiste dans la création d'un contrôle et illustre certaines notions de base ATL du processus.  
  
 [introduction à COM et à ATL](../atl/introduction-to-com-and-atl.md)  
 Présente les principaux concepts derrière le modèle COM \(component object model \(COM\).  Cet article explique brièvement également ce qu'est ATL et quand utiliser.  
  
 [Notions de base des objets COM ATL](../atl/fundamentals-of-atl-com-objects.md)  
 Décrit la relation entre différentes classes ATL et comment ces classes sont implémentées.  
  
 [interfaces doubles et ATL](../atl/dual-interfaces-and-atl.md)  
 Décrit les interfaces doubles du point de vue ATL.  
  
 [Collections et énumérateurs ATL](../atl/atl-collections-and-enumerators.md)  
 Décrit l'implémentation et la création de collections et des énumérateurs dans ATL.  
  
 [Notions de base du contrôle composite](../atl/atl-composite-control-fundamentals.md)  
 Fournit des instructions pas \- à \- pas pour créer un contrôle composite.  Un contrôle composite est un type de contrôle ActiveX qui peut contenir d'autres contrôles Windows ou contrôles ActiveX.  
  
 [FAQ de contenance de contrôles ATL](../atl/atl-control-containment-faq.md)  
 Décrit les problèmes fondamentales liées à l'hébergement de contrôles ATL.  
  
 [Pages de propriétés ATL COM](../atl/atl-com-property-pages.md)  
 Explique comment spécifier et implémenter des pages de propriétés COM.  
  
 [Prise en charge ATL pour les contrôles DHTML](../atl/atl-support-for-dhtml-controls.md)  
 Fournit des instructions pas \- à \- pas pour créer un contrôle DHTML.  
  
 [Points de connexion ATL](../atl/atl-connection-points.md)  
 Explique ce que sont les points de connexion et comment les ATL implémente.  
  
 [gestion des événements et ATL](../atl/event-handling-and-atl.md)  
 Décrit les étapes que vous devez suivre pour gérer des événements COM à l'aide de les classes d' [IDispEventImpl](../atl/reference/idispeventimpl-class.md) et d' [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) ATL.  
  
 [ATL et le marshaleur libre de threads](../atl/atl-and-the-free-threaded-marshaler.md)  
 Fournit des détails en l'option de l'assistant objet simple ATL qui permet à votre classe pour agréger le marshaleur libre de threads \(FTM\).  
  
 [spécifier le modèle de thread du projet](../atl/specifying-the-threading-model-for-a-project-atl.md)  
 Décrit les macros disponibles pour contrôler relié à la performance à l'exécution avec le threading dans votre projet.  
  
 [Classes de module ATL](../atl/atl-module-classes.md)  
 Décrit les classes de module nouvelles pour ATL 7,0.  Les classes de module implémentent les fonctionnalités élémentaires requises par ATL.  
  
 [services d'ATL](../atl/atl-services.md)  
 Décrit la série d'événements qui se produisent lorsqu'un service est implémenté.  Parle également de certains concepts liés au développement un service.  
  
 [Classes de fenêtres ATL](../atl/atl-window-classes.md)  
 Décrit comment créer, et surclassement fenêtres de sous\-classe dans ATL.  Les classes de fenêtres ATL ne sont pas des classes COM.  
  
 [Classes de collection ATL](../atl/atl-collection-classes.md)  
 Décrit comment utiliser des tableaux et des cartes de ATL.  
  
 [Le composant de Registre ATL \(registre\)](../atl/atl-registry-component-registrar.md)  
 Décrit la syntaxe de script ATL et les paramètres remplaçables.  Il montre également comment configurer un lien statique au registre.  
  
 [Programmation avec ATL et le code du runtime C](../atl/programming-with-atl-and-c-run-time-code.md)  
 Décrit les avantages de lier statiquement ou dynamiquement à la bibliothèque runtime C \(CRT\).  
  
 [programmation avec CComBSTR](../atl/programming-with-ccombstr-atl.md)  
 Décrit plusieurs situations qui requièrent l'avertissement lors de la programmation avec `CComBSTR`.  
  
 [Référence d'encodage](../atl/atl-encoding-reference.md)  
 Fournit des fonctions et des macros qui prennent en charge l'encodage dans une plage des normes web courants tels que l'uuencode, hexadécimal, et UTF8 dans l'atlenc.h.  
  
 [Référence des utilitaires](../atl/atl-utilities-reference.md)  
 Fournit le code pour les chemins et manipulation des URL sous forme de [CPathT](../atl/reference/cpatht-class.md) et d' [Aller\-retour](../atl/reference/curl-class.md).  Un pool de threads, [CThreadPool](../atl/reference/cthreadpool-class.md), peut être utilisé dans vos propres applications.  Ce code se trouve dans atlpath.h et atlutil.h.  
  
## Rubriques connexes  
 [Exemples ATL](../top/visual-cpp-samples.md)  
 Fournit des descriptions de et des liens vers des exemples de programme ATL.  
  
 [créer un projet ATL](../atl/reference/creating-an-atl-project.md)  
 Contient des informations sur l'Assistant Projet ATL.  
  
 [Assistant Contrôle ATL](../atl/reference/atl-control-wizard.md)  
 Explique comment ajouter des classes.  
  
 [programmation par attributs](../windows/attributed-programming-concepts.md)  
 Fournit une vue d'ensemble sur l'utilisation des attributs pour simplifier la programmation COM plus une liste de liens vers des rubriques plus détaillées.  
  
 [Vue d'ensemble de la classe ATL](../atl/atl-class-overview.md)  
 Fournit des informations de référence et les liens à ATL classe.