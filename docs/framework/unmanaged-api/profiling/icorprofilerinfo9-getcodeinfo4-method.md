---
title: ICorProfilerInfo9::GetCodeInfo4
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetCodeInfo4
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: ce29703a181106353695414e8b291b14c697fc56
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444798"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a>ICorProfilerInfo9：： GetCodeInfo4 方法

给定本机代码起始地址，返回存储此代码的虚拟内存块。

## <a name="syntax"></a>语法

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

#### <a name="parameters"></a>参数

`pNativeCodeStartAddress` \
中指向本机函数开头的指针。

`cCodeInfos` \
[in] `codeInfos` 数组的大小。

`pcCodeInfos` \
弄指向可用[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)结构总数的指针。

`codeInfos` \
[out] 调用方提供的缓冲区。 返回此方法后，它包含一个 `COR_PRF_CODE_INFO` 结构数组，每个结构描述一个本机代码块。

## <a name="remarks"></a>备注

`GetCodeInfo4` 方法类似于[GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)，只不过它可以查找方法的不同本机版本的代码信息。

> [!NOTE]
> `GetCodeInfo4` 可以触发垃圾回收。

范围按公共中间语言 (CIL) 偏移递增的顺序进行排序。

`GetCodeInfo4` 返回后，必须验证 `codeInfos` 缓冲区是否足够大，以便包含所有[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)结构。 为此，请将 `cCodeInfos` 的值和 `cchName` 参数的值进行比较。 如果 `cCodeInfos` 除以[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)结构的大小小于 `pcCodeInfos`，则分配一个较大的 `codeInfos` 缓冲区，使用新的、更大的大小更新 `cCodeInfos`，然后再次调用 `GetCodeInfo4`。

或者，可以先用长度为零的 `GetCodeInfo4` 缓冲区调用 `codeInfos` 以获取正确的缓冲区大小。 然后，可以将 `codeInfos` 缓冲区大小设置为 `pcCodeInfos`中返回的值，再乘以[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)结构的大小，然后再次调用 `GetCodeInfo4`。

## <a name="requirements"></a>要求

**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)。

**头文件：** CorProf.idl、CorProf.h

**库：** CorGuids.lib

**.Net 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo9 接口](../../../../docs/framework/unmanaged-api/profiling/ICorProfilerInfo9-interface.md)
