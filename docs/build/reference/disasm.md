---
title: /DISASM | Microsoft Docs
ms.date: 1/17/2018
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /disasm
dev_langs: C++
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d448b92c3436f3d2875bd8d9b8e0af6a7149e065
ms.sourcegitcommit: ff9bf140b6874bc08718674c07312ecb5f996463
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2018
---
# <a name="disasm"></a>/DISASM

Imprimer le code machine des sections de code dans la sortie DUMPBIN.

## <a name="syntax"></a>Syntaxe

> **/DISASM**{**:**\[**BYTES**|**NOBYTES**]}  

### <a name="arguments"></a>Arguments

**BYTES**  
Inclut les octets de l’instruction avec les opcodes interprétées et les arguments dans la sortie du code machine. Il s'agit de l'option par défaut.

**NOBYTES**  
N’inclut pas les octets de l’instruction dans la sortie du code machine.

## <a name="remarks"></a>Notes

Le **/DISASM** option affiche le code machine des sections de code dans le fichier. Il utilise les symboles de débogage s’ils sont présents dans le fichier.

**/DISASM** doit uniquement être utilisée sur des images natives non managés,. L’outil équivalent pour le code managé est [ILDASM](/dotnet/framework/tools/ildasm-exe-il-disassembler).

Uniquement les [/HEADERS](../../build/reference/headers.md) (option DUMPBIN) est disponible pour les fichiers générés par le [/GL (optimisation de l’ensemble du programme)](../../build/reference/gl-whole-program-optimization.md) option du compilateur.

## <a name="see-also"></a>Voir aussi

[DUMPBIN, options](../../build/reference/dumpbin-options.md)  
