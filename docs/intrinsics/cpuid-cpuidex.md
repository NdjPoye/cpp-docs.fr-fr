---
title: __cpuid, __cpuidex | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __cpuid_cpp
- __cpuid
dev_langs: C++
helpviewer_keywords:
- __cpuid intrinsic
- cpuid instruction
- cpuid intrinsic
ms.assetid: f8c344d3-91bf-405f-8622-cb0e337a6bdc
caps.latest.revision: "38"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cc20732fa9a79765f4cd56e53ddd990a4d1ea1a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cpuid-cpuidex"></a>__cpuid, __cpuidex
**Section spécifique à Microsoft**  
  
 Génère l'instruction `cpuid` qui est disponible sur x86 et [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]. Cette instruction interroge le processeur pour obtenir des informations sur les fonctionnalités prises en charge et le type d’UC.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void __cpuid(  
   int cpuInfo[4],  
   int function_id  
);  
  
void __cpuidex(  
   int cpuInfo[4],  
   int function_id,  
   int subfunction_id  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `cpuInfo`  
 Tableau de quatre entiers qui contient les informations retournées dans EAX, EBX, ECX et EDX au sujet des fonctionnalités prises en charge de l'UC.  
  
 [in] `function_id`  
 Code qui spécifie des informations à récupérer, passées dans EAX.  
  
 [in] `subfunction_id`  
 Code supplémentaire qui spécifie des informations à récupérer, passées dans ECX.  
  
## <a name="requirements"></a>Configuration requise  
  
|Intrinsèque|Architecture|  
|---------------|------------------|  
|`__cpuid`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`__cpuidex`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d’en-tête** \<intrin.h >  
  
## <a name="remarks"></a>Notes  
 Cet intrinsèque stocke les fonctionnalités prises en charge et les informations d'UC retournées par l'instruction `cpuid` dans `cpuInfo`, un tableau de quatre entiers 32 bits rempli avec les valeurs des registres EAX, EBX, ECX et EDX (dans cet ordre). Les informations retournées ont une signification différente en fonction de la valeur passée en tant que paramètre `function_id`. Les informations retournées avec diverses valeurs de `function_id` dépendent du processeur.  
  
 L'intrinsèque `__cpuid` efface le registre ECX avant d'appeler l'instruction `cpuid`. L'intrinsèque `__cpuidex` définit la valeur du registre ECX sur `subfunction_id` avant de générer l'instruction `cpuid`. Cela vous permet de rassembler des informations supplémentaires sur le processeur.  
  
 Pour plus d’informations sur les paramètres spécifiques à utiliser et les valeurs retournées par ces fonctions intrinsèques sur les processeurs Intel, consultez la documentation relative à la `cpuid` instruction [Intel 64 et IA-32 Architectures Software développeurs manuel Volume 2 : Instruction Set référence](http://go.microsoft.com/fwlink/p/?LinkID=510021) et [référence de programmation des Extensions du jeu d’instructions d’Architecture Intel](http://go.microsoft.com/fwlink/p/?LinkID=506627). La documentation Intel utilise les termes « feuille » et « sous-feuille » pour les paramètres `function_id` et `subfunction_id` passés dans EAX et ECX.  
  
 Pour plus d’informations sur les paramètres spécifiques à utiliser et les valeurs retournées par ces fonctions intrinsèques sur les processeurs AMD, consultez la documentation relative à la `cpuid` instruction [Manual Volume 3 du programmeur AMD64 Architecture : À usage général et Instructions système](http://go.microsoft.com/fwlink/p/?LinkId=510023) et dans le [révision Guides](http://go.microsoft.com/fwlink/p/?LinkId=510023) de familles de processeur spécifique. La documentation AMD utilise les termes « numéro de fonction » et « numéro de sous-fonction » pour les paramètres `function_id` et `subfunction_id` passés dans EAX et ECX.  
  
 Quand l'argument `function_id` a la valeur 0, `cpuInfo[0]` renvoie le `function_id` non étendu le plus élevé disponible pris en charge par le processeur. Le fabricant du processeur est encodé dans `cpuInfo[1]`, `cpuInfo[2]` et cpuInfo [3].  
  
 La prise en charge des extensions du jeu d'instructions et des fonctionnalités du processeur spécifiques est encodée dans les résultats `cpuInfo` renvoyés pour les valeurs function_id supérieures. Pour plus d'informations, consultez les manuels mentionnés ci-dessus et l'exemple de code suivant.  
  
 Certains processeurs prennent en charge les informations CPUID des fonctions étendues. Dans ce cas, les valeurs `function_id` à partir de 0x80000000 peuvent être utilisées pour retourner des informations. Pour déterminer la valeur significative maximale autorisée, affectez à `function_id` la valeur 0x80000000. La valeur maximale de `function_id` prise en charge pour les fonctions étendues sera écrite dans `cpuInfo[0]`.  
  
## <a name="example"></a>Exemple  
 Cet exemple montre certaines des informations disponibles par l'intermédiaire des intrinsèques `__cpuid` et `__cpuidex`. L'application répertorie les extensions du jeu d'instructions prises en charge par le processeur actuel. La sortie montre un résultat possible pour un processeur particulier.  
  
```  
// InstructionSet.cpp   
// Compile by using: cl /EHsc /W4 InstructionSet.cpp  
// processor: x86, x64  
// Uses the __cpuid intrinsic to get information about   
// CPU extended instruction set support.  
  
#include <iostream>  
#include <vector>  
#include <bitset>  
#include <array>  
#include <string>  
#include <intrin.h>  
  
class InstructionSet  
{  
    // forward declarations  
    class InstructionSet_Internal;  
  
public:  
    // getters  
    static std::string Vendor(void) { return CPU_Rep.vendor_; }  
    static std::string Brand(void) { return CPU_Rep.brand_; }  
  
    static bool SSE3(void) { return CPU_Rep.f_1_ECX_[0]; }  
    static bool PCLMULQDQ(void) { return CPU_Rep.f_1_ECX_[1]; }  
    static bool MONITOR(void) { return CPU_Rep.f_1_ECX_[3]; }  
    static bool SSSE3(void) { return CPU_Rep.f_1_ECX_[9]; }  
    static bool FMA(void) { return CPU_Rep.f_1_ECX_[12]; }  
    static bool CMPXCHG16B(void) { return CPU_Rep.f_1_ECX_[13]; }  
    static bool SSE41(void) { return CPU_Rep.f_1_ECX_[19]; }  
    static bool SSE42(void) { return CPU_Rep.f_1_ECX_[20]; }  
    static bool MOVBE(void) { return CPU_Rep.f_1_ECX_[22]; }  
    static bool POPCNT(void) { return CPU_Rep.f_1_ECX_[23]; }  
    static bool AES(void) { return CPU_Rep.f_1_ECX_[25]; }  
    static bool XSAVE(void) { return CPU_Rep.f_1_ECX_[26]; }  
    static bool OSXSAVE(void) { return CPU_Rep.f_1_ECX_[27]; }  
    static bool AVX(void) { return CPU_Rep.f_1_ECX_[28]; }  
    static bool F16C(void) { return CPU_Rep.f_1_ECX_[29]; }  
    static bool RDRAND(void) { return CPU_Rep.f_1_ECX_[30]; }  
  
    static bool MSR(void) { return CPU_Rep.f_1_EDX_[5]; }  
    static bool CX8(void) { return CPU_Rep.f_1_EDX_[8]; }  
    static bool SEP(void) { return CPU_Rep.f_1_EDX_[11]; }  
    static bool CMOV(void) { return CPU_Rep.f_1_EDX_[15]; }  
    static bool CLFSH(void) { return CPU_Rep.f_1_EDX_[19]; }  
    static bool MMX(void) { return CPU_Rep.f_1_EDX_[23]; }  
    static bool FXSR(void) { return CPU_Rep.f_1_EDX_[24]; }  
    static bool SSE(void) { return CPU_Rep.f_1_EDX_[25]; }  
    static bool SSE2(void) { return CPU_Rep.f_1_EDX_[26]; }  
  
    static bool FSGSBASE(void) { return CPU_Rep.f_7_EBX_[0]; }  
    static bool BMI1(void) { return CPU_Rep.f_7_EBX_[3]; }  
    static bool HLE(void) { return CPU_Rep.isIntel_ && CPU_Rep.f_7_EBX_[4]; }  
    static bool AVX2(void) { return CPU_Rep.f_7_EBX_[5]; }  
    static bool BMI2(void) { return CPU_Rep.f_7_EBX_[8]; }  
    static bool ERMS(void) { return CPU_Rep.f_7_EBX_[9]; }  
    static bool INVPCID(void) { return CPU_Rep.f_7_EBX_[10]; }  
    static bool RTM(void) { return CPU_Rep.isIntel_ && CPU_Rep.f_7_EBX_[11]; }  
    static bool AVX512F(void) { return CPU_Rep.f_7_EBX_[16]; }  
    static bool RDSEED(void) { return CPU_Rep.f_7_EBX_[18]; }  
    static bool ADX(void) { return CPU_Rep.f_7_EBX_[19]; }  
    static bool AVX512PF(void) { return CPU_Rep.f_7_EBX_[26]; }  
    static bool AVX512ER(void) { return CPU_Rep.f_7_EBX_[27]; }  
    static bool AVX512CD(void) { return CPU_Rep.f_7_EBX_[28]; }  
    static bool SHA(void) { return CPU_Rep.f_7_EBX_[29]; }  
  
    static bool PREFETCHWT1(void) { return CPU_Rep.f_7_ECX_[0]; }  
  
    static bool LAHF(void) { return CPU_Rep.f_81_ECX_[0]; }  
    static bool LZCNT(void) { return CPU_Rep.isIntel_ && CPU_Rep.f_81_ECX_[5]; }  
    static bool ABM(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_ECX_[5]; }  
    static bool SSE4a(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_ECX_[6]; }  
    static bool XOP(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_ECX_[11]; }  
    static bool TBM(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_ECX_[21]; }  
  
    static bool SYSCALL(void) { return CPU_Rep.isIntel_ && CPU_Rep.f_81_EDX_[11]; }  
    static bool MMXEXT(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_EDX_[22]; }  
    static bool RDTSCP(void) { return CPU_Rep.isIntel_ && CPU_Rep.f_81_EDX_[27]; }  
    static bool _3DNOWEXT(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_EDX_[30]; }  
    static bool _3DNOW(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_EDX_[31]; }  
  
private:  
    static const InstructionSet_Internal CPU_Rep;  
  
    class InstructionSet_Internal  
    {  
    public:  
        InstructionSet_Internal()  
            : nIds_{ 0 },  
            nExIds_{ 0 },  
            isIntel_{ false },  
            isAMD_{ false },  
            f_1_ECX_{ 0 },  
            f_1_EDX_{ 0 },  
            f_7_EBX_{ 0 },  
            f_7_ECX_{ 0 },  
            f_81_ECX_{ 0 },  
            f_81_EDX_{ 0 },  
            data_{},  
            extdata_{}  
        {  
            //int cpuInfo[4] = {-1};  
            std::array<int, 4> cpui;  
  
            // Calling __cpuid with 0x0 as the function_id argument  
            // gets the number of the highest valid function ID.  
            __cpuid(cpui.data(), 0);  
            nIds_ = cpui[0];  
  
            for (int i = 0; i <= nIds_; ++i)  
            {  
                __cpuidex(cpui.data(), i, 0);  
                data_.push_back(cpui);  
            }  
  
            // Capture vendor string  
            char vendor[0x20];  
            memset(vendor, 0, sizeof(vendor));  
            *reinterpret_cast<int*>(vendor) = data_[0][1];  
            *reinterpret_cast<int*>(vendor + 4) = data_[0][3];  
            *reinterpret_cast<int*>(vendor + 8) = data_[0][2];  
            vendor_ = vendor;  
            if (vendor_ == "GenuineIntel")  
            {  
                isIntel_ = true;  
            }  
            else if (vendor_ == "AuthenticAMD")  
            {  
                isAMD_ = true;  
            }  
  
            // load bitset with flags for function 0x00000001  
            if (nIds_ >= 1)  
            {  
                f_1_ECX_ = data_[1][2];  
                f_1_EDX_ = data_[1][3];  
            }  
  
            // load bitset with flags for function 0x00000007  
            if (nIds_ >= 7)  
            {  
                f_7_EBX_ = data_[7][1];  
                f_7_ECX_ = data_[7][2];  
            }  
  
            // Calling __cpuid with 0x80000000 as the function_id argument  
            // gets the number of the highest valid extended ID.  
            __cpuid(cpui.data(), 0x80000000);  
            nExIds_ = cpui[0];  
  
            char brand[0x40];  
            memset(brand, 0, sizeof(brand));  
  
            for (int i = 0x80000000; i <= nExIds_; ++i)  
            {  
                __cpuidex(cpui.data(), i, 0);  
                extdata_.push_back(cpui);  
            }  
  
            // load bitset with flags for function 0x80000001  
            if (nExIds_ >= 0x80000001)  
            {  
                f_81_ECX_ = extdata_[1][2];  
                f_81_EDX_ = extdata_[1][3];  
            }  
  
            // Interpret CPU brand string if reported  
            if (nExIds_ >= 0x80000004)  
            {  
                memcpy(brand, extdata_[2].data(), sizeof(cpui));  
                memcpy(brand + 16, extdata_[3].data(), sizeof(cpui));  
                memcpy(brand + 32, extdata_[4].data(), sizeof(cpui));  
                brand_ = brand;  
            }  
        };  
  
        int nIds_;  
        int nExIds_;  
        std::string vendor_;  
        std::string brand_;  
        bool isIntel_;  
        bool isAMD_;  
        std::bitset<32> f_1_ECX_;  
        std::bitset<32> f_1_EDX_;  
        std::bitset<32> f_7_EBX_;  
        std::bitset<32> f_7_ECX_;  
        std::bitset<32> f_81_ECX_;  
        std::bitset<32> f_81_EDX_;  
        std::vector<std::array<int, 4>> data_;  
        std::vector<std::array<int, 4>> extdata_;  
    };  
};  
  
// Initialize static member data  
const InstructionSet::InstructionSet_Internal InstructionSet::CPU_Rep;  
  
// Print out supported instruction set extensions  
int main()  
{  
    auto& outstream = std::cout;  
  
    auto support_message = [&outstream](std::string isa_feature, bool is_supported) {  
        outstream << isa_feature << (is_supported ? " supported" : " not supported") << std::endl;  
    };  
  
    std::cout << InstructionSet::Vendor() << std::endl;  
    std::cout << InstructionSet::Brand() << std::endl;  
  
    support_message("3DNOW",       InstructionSet::_3DNOW());  
    support_message("3DNOWEXT",    InstructionSet::_3DNOWEXT());  
    support_message("ABM",         InstructionSet::ABM());  
    support_message("ADX",         InstructionSet::ADX());  
    support_message("AES",         InstructionSet::AES());  
    support_message("AVX",         InstructionSet::AVX());  
    support_message("AVX2",        InstructionSet::AVX2());  
    support_message("AVX512CD",    InstructionSet::AVX512CD());  
    support_message("AVX512ER",    InstructionSet::AVX512ER());  
    support_message("AVX512F",     InstructionSet::AVX512F());  
    support_message("AVX512PF",    InstructionSet::AVX512PF());  
    support_message("BMI1",        InstructionSet::BMI1());  
    support_message("BMI2",        InstructionSet::BMI2());  
    support_message("CLFSH",       InstructionSet::CLFSH());  
    support_message("CMPXCHG16B",  InstructionSet::CMPXCHG16B());  
    support_message("CX8",         InstructionSet::CX8());  
    support_message("ERMS",        InstructionSet::ERMS());  
    support_message("F16C",        InstructionSet::F16C());  
    support_message("FMA",         InstructionSet::FMA());  
    support_message("FSGSBASE",    InstructionSet::FSGSBASE());  
    support_message("FXSR",        InstructionSet::FXSR());  
    support_message("HLE",         InstructionSet::HLE());  
    support_message("INVPCID",     InstructionSet::INVPCID());  
    support_message("LAHF",        InstructionSet::LAHF());  
    support_message("LZCNT",       InstructionSet::LZCNT());  
    support_message("MMX",         InstructionSet::MMX());  
    support_message("MMXEXT",      InstructionSet::MMXEXT());  
    support_message("MONITOR",     InstructionSet::MONITOR());  
    support_message("MOVBE",       InstructionSet::MOVBE());  
    support_message("MSR",         InstructionSet::MSR());  
    support_message("OSXSAVE",     InstructionSet::OSXSAVE());  
    support_message("PCLMULQDQ",   InstructionSet::PCLMULQDQ());  
    support_message("POPCNT",      InstructionSet::POPCNT());  
    support_message("PREFETCHWT1", InstructionSet::PREFETCHWT1());  
    support_message("RDRAND",      InstructionSet::RDRAND());  
    support_message("RDSEED",      InstructionSet::RDSEED());  
    support_message("RDTSCP",      InstructionSet::RDTSCP());  
    support_message("RTM",         InstructionSet::RTM());  
    support_message("SEP",         InstructionSet::SEP());  
    support_message("SHA",         InstructionSet::SHA());  
    support_message("SSE",         InstructionSet::SSE());  
    support_message("SSE2",        InstructionSet::SSE2());  
    support_message("SSE3",        InstructionSet::SSE3());  
    support_message("SSE4.1",      InstructionSet::SSE41());  
    support_message("SSE4.2",      InstructionSet::SSE42());  
    support_message("SSE4a",       InstructionSet::SSE4a());  
    support_message("SSSE3",       InstructionSet::SSSE3());  
    support_message("SYSCALL",     InstructionSet::SYSCALL());  
    support_message("TBM",         InstructionSet::TBM());  
    support_message("XOP",         InstructionSet::XOP());  
    support_message("XSAVE",       InstructionSet::XSAVE());  
}  
```  
  
```Output  
GenuineIntel  
        Intel(R) Core(TM) i5-2500 CPU @ 3.30GHz  
3DNOW not supported  
3DNOWEXT not supported  
ABM not supported  
ADX not supported  
AES supported  
AVX supported  
AVX2 not supported  
AVX512CD not supported  
AVX512ER not supported  
AVX512F not supported  
AVX512PF not supported  
BMI1 not supported  
BMI2 not supported  
CLFSH supported  
CMPXCHG16B supported  
CX8 supported  
ERMS not supported  
F16C not supported  
FMA not supported  
FSGSBASE not supported  
FXSR supported  
HLE not supported  
INVPCID not supported  
LAHF supported  
LZCNT not supported  
MMX supported  
MMXEXT not supported  
MONITOR not supported  
MOVBE not supported  
MSR supported  
OSXSAVE supported  
PCLMULQDQ supported  
POPCNT supported  
PREFETCHWT1 not supported  
RDRAND not supported  
RDSEED not supported  
RDTSCP supported  
RTM not supported  
SEP supported  
SHA not supported  
SSE supported  
SSE2 supported  
SSE3 supported  
SSE4.1 supported  
SSE4.2 supported  
SSE4a not supported  
SSSE3 supported  
SYSCALL supported  
TBM not supported  
XOP not supported  
XSAVE supported  
  
```  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [compilateur, fonctions intrinsèques](../intrinsics/compiler-intrinsics.md)