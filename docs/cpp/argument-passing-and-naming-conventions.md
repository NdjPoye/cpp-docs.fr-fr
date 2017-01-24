---
title: "Passage des arguments et conventions de d&#233;nomination | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "passage d'argument (C++), conventions"
  - "arguments (C++), affecter des noms"
  - "arguments (C++), passer"
  - "arguments (C++), étendue"
  - "conventions de codage, arguments"
  - "conventions (C++), noms d'arguments"
  - "conventions d'affectation de noms (C++), arguments"
  - "passer des arguments, conventions"
  - "registres, valeurs de retour"
  - "thiscall (mot clé) (C++)"
ms.assetid: de468979-eab8-4158-90c5-c198932f93b9
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Passage des arguments et conventions de d&#233;nomination
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Les compilateurs Visual C\+\+ vous permettent de spécifier des conventions pour passer des arguments et des valeurs de retour entre des fonctions et des appelants.  Les conventions ne sont pas toutes disponibles sur toutes les plateformes prises en charge et certaines conventions utilisent des implémentations spécifiques à la plateforme.  Dans la plupart des cas, les mots clés ou les commutateurs de compilation qui spécifient une convention non prise en charge sur une plateforme spécifique sont ignorés et la convention par défaut de la plateforme est utilisée.  
  
 Sur les plateformes x86, tous les arguments sont élargis à 32 bits lorsqu'ils sont passés.  Les valeurs de retour sont également élargies à 32 bits et retournées dans le registre EAX, sauf pour les structures de 8 octets, qui sont retournées dans la paire de registres EDX:EAX.  Les structures plus grandes sont retournées dans le registre EAX comme pointeurs vers des structures de retour masquées.  Les paramètres font l'objet d'un push sur la pile de droite à gauche.  Les structures qui ne sont pas des POD ne sont pas retournées dans les registres.  
  
 Le compilateur génère du code de prologue et d'épilogue pour enregistrer et restaurer les registres ESI, EDI, EBX et EBP, s'ils sont utilisés dans la fonction.  
  
> [!NOTE]
>  Lorsqu'un struct, une union ou une classe est retourné\(e\) à partir d'une fonction par valeur, toutes les définitions du type doivent être identiques, sinon le programme peut échouer au moment de l'exécution.  
  
 Pour plus d'informations sur la façon de définir votre propre code de prologue et d'épilogue de fonction, consultez la rubrique [Appels de fonction naked](../cpp/naked-function-calls.md).  
  
 Pour plus d'informations sur les conventions d'appel par défaut dans le code qui cible les plateformes x64, consultez [Vue d'ensemble des conventions d'appel x64](../build/overview-of-x64-calling-conventions.md).  Pour plus d'informations sur les problèmes de convention d'appel dans le code qui cible les plateformes ARM, consultez [Problèmes courants de migration ARM Visual C\+\+](../build/common-visual-cpp-arm-migration-issues.md).  
  
 Les conventions d'appel suivantes sont prises en charge par le compilateur Visual C\/C\+\+.  
  
|Mot clé|Nettoyage de pile|Passage de paramètres|  
|-------------|-----------------------|---------------------------|  
|[\_\_cdecl](../cpp/cdecl.md)|Appelant|Effectue un push des paramètres sur la pile, dans l'ordre inverse \(de droite à gauche\)|  
|[\_\_clrcall](../cpp/clrcall.md)|N\/A|Charger les paramètres sur la pile d'expression CLR dans l'ordre \(de gauche à droite\).|  
|[\_\_stdcall](../cpp/stdcall.md)|Appelé|Effectue un push des paramètres sur la pile, dans l'ordre inverse \(de droite à gauche\)|  
|[\_\_fastcall](../cpp/fastcall.md)|Appelé|Stocké dans les registres, puis fait l'objet d'un push sur la pile|  
|[\_\_thiscall](../cpp/thiscall.md)|Appelé|Fait l'objet d'un push sur la pile ; pointeur **this** stocké dans ECX|  
|[\_\_vectorcall](../cpp/vectorcall.md)|Appelé|Stocké dans les registres, puis fait l'objet d'un push sur la pile dans l'ordre inverse \(de droite à gauche\)|  
  
 Pour plus d'informations, consultez [Conventions d'appels obsolètes](../cpp/obsolete-calling-conventions.md).  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Conventions d'appel](../cpp/calling-conventions.md)