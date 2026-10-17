# step1
### 1.1
1. CPU、GPU、主板是什么，他们分别提供什么，有什么功能？
* 主板就是一块电路板，它负责连接并协调各种硬件设备，比如CPU、GPU、内存、硬盘等。如果没有主板，CPU和GPU等就没有地方放了。它是电脑的骨架和交通枢纽，把所有硬件连起来。提供物理接口：各种插槽、插口，通信通道：总线、芯片组，还能给硬件供电。
* CPU（中央处理器），是电脑的核心大脑，由控制器和运算器构成，负责执行指令、做运算、控制全局。它具有强大的计算能力，控制其它硬件干活，执行程序代码，运算速度极快。主要步骤是从内存取指令，读取指令，再发指令取数据，把数据再ALU运算完后又返回给寄存器活内存，更新准备下一条指令。
* GPU（图形处理器），专门做“大量重复计算”的处理器，最初用来画图，现在也用来跑 AI。常说的显卡核心部分就是GPU，它能进行大规模并行计算，完成图形渲染和矩阵计算，虽然单个并不快，但核心多，所以很适合用来运算。
2. 手机上常说的 512G内存 和电脑上的 16G内存 是一回事吗？内存、主存、存储到底分别是什么？有什么区别？
* 不一样。手机的内存说的是存储空间，电脑的内存就是它的运行内存，完全不一样。手机的内存相当于电脑的磁盘空间，电脑的内存相当于手机的运行内存。内存 = 运行内存 = 主存，临时存放正在运行的程序和数据，但断电就丢，速度快，容量小，电脑上叫“内存条”，手机上也叫“运行内存”，相当于是个临时工作台。存储 = 外存 = 硬盘 = 存储空间，长期存放数据，比如系统、软件、照片、视频等，特点是断电不丢，电脑上叫硬盘，手机上叫存储空间。在计算机体系结构里，主存就是内存RAM，和它对应的是辅存（辅助存储器），也就是硬盘。
3. 电源要注意什么？
* 电源功率要够，也要留余量。否则会缩短电脑寿命。看“额定功率”，不看“峰值功率”，一般电脑都是额定功率。看电源转换效率认证，效率越高，发热越少，越省电。另外接口也要够用。
4. 7 处理器一定比 i5 处理器强吗？30系的显卡和 40 系的相比呢？处理器和显卡的性能究竟怎么看？
* 不一定。i7不一定比i5强，40系也不一定全面碾压30系。
* 看处理器要综合定位，代际和具体型号来看。同代i7通常比i5强，但跨代就完全不同了高代的完全可以比上低代的。优先看代际，代际越高越好，接着看定位是i几，最后看同代内性能等级越高越好。
* CPU具体要看核心/线程数，主频/睿频，缓存（L3），架构/代际等。GPU具体看核心数，显存容量，核心频率等。
5. 把老板这套配置里所有的坑找出来，让他见识一下你的实力。
* 大牌主板没有具体说，可能是低端缩水板。
* i7级CPU，没说代际，可能是山寨的，可能比i3还弱，不是真i7。
* 高端内存，可能是杂牌，没说具体什么型号内存。
* 豪华GPU，不说型号，可能是矿卡/低端卡。
* 512G内存手机，混淆内存和存储。
* 1.25T硬盘，标准是1T，可能是机械盘或杂牌。
### 1.2
1. 常见的存储介质（如 SRAM、DRAM、NAND Flash、HDD）分别应用在计算机的哪些部件中？分别有什么特点？这样的特点起到了什么作用？
* SRAM即静态随机存储器，在CPU中，也就是缓存，速度快，容量小，断电丢失，结构是六个晶体管存一位，很贵。作用是给CPU提供最快的数据访问，减少等待内存的时间。CPU 速度远快于内存，如果每次都等内存，CPU 会闲置。SRAM 做缓存，把常用数据放身边，CPU需要时优先访问缓存，以匹配CPU的运行速度。
* DRAM（动态随机存储器），在内存条中，速度快但没SRAM快，容量较大GB级别，断电丢失，作用是存放正在运行的程序和数据。内存是 CPU 和硬盘之间的“中转站”。CPU不断从内存中读取指令和数据，内存中数据来于硬盘。内存相当于一个临时工作台。
* NAND Flash（闪存），用在：SSD、U 盘、手机存储、SD 卡。速度较快，容量大，断电不丢失，所以它作为长期存放数据的地方。
* HDD（机械硬盘），用在：大容量存储、备份、监控等中。速度慢，容量大，断电不丢失，结构是磁盘 + 磁头，机械运动。因为很不方便，所以用来存不常用的大文件和数据。
2. 寄存器、高速缓存、只读存储器是什么，位于电脑的哪个地方？
* CPU 内部最快的存储单元，用来暂存指令、数据和地址。位于CPU内部，和运算器直接相连，暂存CPU要处理的数据，速度很快，但容量很小。
* 高速缓存（cache）是CPU内部的高速存储器，用来缓存内存中的数据。在 CPU 内部，比寄存器稍远，但比内存，分为三级缓存。CPU要读数据，先查缓存，命中就直接用，不用等内存，大幅减少CPU等待内存的时间。
* 只读存储器（ROM）是只能读、不能随便写的存储器，断电不丢失。在主板上，不在 CPU 里。作用是存开机启动的固件BIOS以及固定程序。开机时，CPU从ROM读BIOS程序、BIOS初始化硬件，再加载操作系统，完成启动。
3. DRAM 的物理结构决定了它需要不断“刷新”才能保住数据，那么 DRAM 的结构是怎样的？ DRAM 的基本工作原理又是怎样的？
* 首先DRAM最基本的一个存储单元是由由一个晶体管和电容组成，晶体管相当于一个开关，电容有点相当于1，无电相当于0，这样一个存储单元存1位。DRAM不是一个单元，而是一种矩阵结构，横向通过字线连接，纵向通过位线连接。字线控制整行晶体管的开与关，位线读出或写入一列数据。有读和写两种操作。读操作是选中字线，晶体管连通，电容连上位线，随后电荷流出，放大器读取出0或1。但这会破坏电容里的电荷（电荷流出去了），所以必须重新充电。写操作是选中字线，位线加电压，电荷充进电容（写1）流出（写0），最后关闭字线，电容保留电荷，就是给电容充电或放电。还有一个是刷新。由于电容会放电导致电荷流失，存储的数据就会消失，这个过程很快。所以需要不断执行读出写会的操作，不断充电放电，保持电容的电荷不变，这个过程就是刷新。
4. Cache（高速缓存）的根本原理是什么？
* Cathe基于程序的局部性原理。将主存中近期可能被CPU访问的数据拷贝到告诉SRAM中；CPU访问时优先查询Cathe，命中则直接读取，未命中则访问主存，以此减少低速主存访问，提升CPU整体运行速度。
* 局部性原理：时间局部性；刚刚被用过的数据，很有可能再次被用，放在cathe中，方便下一次用。空间局部性：刚刚被用过的数据，旁边的数据很有可能再次被用。比如数组。于是缓存就把这些数据都进去，而且缓存是一块一块的读，这一块叫作缓存行，通常是64字节，根据空间局部性，读的时候就把旁边的都读进去了，存在缓存行中。
5. 假设你需要编写一个矩阵乘法程序来暴力破解密码，依据Cache的根本原理，如何优化矩阵乘法程序呢？请简述你的优化方案，并说说运用了Cache的哪个原理。
* 将矩阵分块进行运算，把一个矩阵分成一小块一小块相乘。根据时间局限性，每个块都要进行多次运算，数据进行多次使用。根据空间局限性，每一横块都可以存在一个缓冲行中，存在相邻位置，一个块用到旁边的块必定也要用到。
# step2
### 2.1
1. 什么是虚拟地址？什么是物理地址？操作系统为什么要引入 “虚拟内存” 这个概念？（请列举至少两点好处）
* 虚拟地址是一个中间层，利用间接地址访问的方法访问物理地址。程序中访问的内存地址不再是实际的物理内存地址，而是一个虚拟地址，然后有操作系统将这个地址映射到合适的物理内存地址上，最终保证程序最终访问的内存地址位于不同区域，达到内存地址空间隔离的效果。
* 物理地址就是内存条上真实存在的、硬件层面的地址。
* 早期计算机运行一个程序会把程序全部存入内存然后运行，导致出现进程地址空间不隔离，没有权限保护；内存使用效率低，需要硬盘的装入装出；运行地址随机分配导致程序运行的地址不确定等问题，于是创建了虚拟内存来解决这些问题。根据虚拟内存的概念，它有一下好处：1.有助于进程内存管理，体现在保证内存完整性，通过对内存的权限控制保证了程序运行的安全。2.数据共享。通过虚拟内存更容易实现数据和内存的共享，比方说页表共享，操作系统只需要将各个进程的虚拟内存指向系统分配的共享内存即可，减小物理内存的占用。3.SWAP。虚拟内存可以帮进程扩充内存。在分配物理内存时将暂时不用的数据放到磁盘上，如有需要的内存先使用，等进程完了在使用这些数据，加载到内存中，实现交换。
2. 每个进程的虚拟地址空间具有什么特性？其大小是多少？
* 独立性：每个进程有自己独自的地址内存空间，互不干扰。
* 连续性：进程看到自己的虚拟内存连续，物理内存可能不连续。
* 隔离性：一个进程无法直接访问另一个进程，设有权限互不干扰。
* 虚拟内存可以大于物理内存，因为有SWAP机制。
* 每个进程都以为自己独占整个内存。
* 针对32位系统，虚拟地址空间大小为4GB，内核空间1GB，用户空间3GB。
3. 虚拟地址空间由什么基本单位组成？该单位的大小是多少？
* 虚拟辞职空间的基本单位是页，把虚拟内存划分成一块一块，每一块就是页，每一页都是连续的虚拟地址，是内存管理的最小单位，可根据页表映射到页框。该单位的大小一般为4KB。
4. 虚拟地址空间中的页可以被划分到哪几个主要的段中？
* 从下到上依次是代码段（存程序指令，记为.text），数据段（存已初始化的数据，包括全局变量，记为.data）,Bss段（存未初始化的数据,记为.bss），堆（动态分配的内存，如malloc，共享库（动态链接库），栈（存局部变量，函数返回地址），内核空间（不松口物理内测，内核代码和数据，与进程相关的数据结构如页表等）。
5. 页和页框是什么？是用来做什么的？它们有什么共同点？
* 页是虚拟内存的每一块，将虚拟内存划分成一小块一小块，每一块就是页。页框同理，就是将物理内存划分成一小块一小块，每一块就是页框。页和页框有一个页表。通过映射将页和页框对应起来，最终保证程序最终访问的物理内存地址位于不同区域，实现独立性。页和页框大小相同，通常是4KB。数量对应，通常是一一映射。每个页和页框都是连续的内存块，都是内存管理的基本单位，都有相应的编号（页码，页框码）。
### 2.2
##### 1
1. 页表是什么？它和页是一个东西吗？
* 页表是一套映射表，每一个页可以映射到一个页框，一块虚拟内存映射到一块物理内存，这个映射的规则就是页表。和页不是一个东西，页是一块虚拟内存，页表是一套映射表，将页码和页框码对应在一起。
2. 请简述 MMU（内存管理单元） 和 TLB（转译后备缓冲区） 在地址翻译中分别扮演了什么角色？
* MMU是是内存管理单元，负责将虚拟地址翻译成物理地址的硬件。CPU发出虚拟地址，MMU将其拆分成页码加上偏移量，拿到页码根据页表找到相应的页框码，再加上偏移量就找到了对应的物理内存空间。TLB是MMU中的高速缓存，把最近的翻译结果缓存在MMU中。MMU在翻译地址时会优先看TLB，如果TLB有相应的翻译记录，直接命中拿到页框码，很快。如果没有，就查页表，访问内存，再将这个过程缓存到MMU中，这个过程相对较慢。
3. 进程用来查找物理页框的单级或多级页表存储在什么地方？用来记录页表 “物理基地址” 的是哪一个特定的寄存器？
* 页表存在物理内存里，MMU 按需读取。单级页表简单但占用内存大，多级页表省内存，按需分配，但需要查找多次，时间换空间。记录物理基地址的是CR3，也叫页目录基址寄存器，存储在物理内存中，它记录了一级页表的位置。查找时先看CR3找到一级页表，如果有二级页表，再看二级页表，最终拿到物理页框码和偏移量，即物理地址。
4. 二级页表是什么？对比单级页表有什么优势？这样的优势是怎样展现的？
* 将页号分成两部分，用两级索引来查表。先查一级页表，找到二级页表的地址，再查二级页表，找到物理页框号，加上偏移量得到物理地址。对比单级页表占用内存少，可以按需分配。优势在于二级页表一级固定4B，二级按需分配。如果一个虚拟地址占用很少的内存，单级页表要占用全部内存，二级页表只需要全部一级页表和少部分二级页表，大大节省了内存。通过稀疏地址空间，实现按需分配，但换来的是查找次数的增加，但通过TLB缓存可以节省部分时间。
5. 二级页表机制下，一个32位的虚拟地址具体被划分为哪三个部分？请说明各个部分的位数及其对应的含义。
* 可以分为一级页号(页目录索引PDE)，二级页号（页表索引PTE）和页内偏移量。
* 一级页号占用10位，用来索引一级页表。可以表示1024个条目，每个条目指向一个二级页表，可以查到二级页表的地址。
* 二级页号占用10位，用来索引二级页表。可以表示1024个条目，每个条目指向最终目标所在的物理页框号。
* 页内偏移量占12位，表示目标数据在目标物理页框内部的具体位置。因为页面大小是4KB（即 2¹² 字节），所以需要12位（从0到4095）来寻址页内的每一个字节。根据二级页表查到的物理页框号加上偏移量就找到了准确的物理地址。
##### 2
```c
#include <stdio.h>
#include <stdint.h>
#include <stdlib.h>
#include <stdbool.h>

#define PAGE_DIR_BITS   10 // 页目录索引位数
#define PAGE_TABLE_BITS 10 // 页表索引位数
#define OFFSET_BITS     12 // 页内偏移位数

#define PAGE_TABLE_SIZE (1 << PAGE_TABLE_BITS) // 1024
#define PAGE_DIR_SIZE   (1 << PAGE_DIR_BITS)   // 1024
#define PAGE_SIZE       (1 << OFFSET_BITS)     // 4096 (4KB)

// 页表项 (PTE - Page Table Entry)
// 包含物理帧号和权限位
typedef struct {
    bool     present_bit; // 存在位：1表示该页在物理内存中，0表示不在
    bool     rw_bit;      // 读写位：1表示可读可写，0表示只读
    uint32_t frame_number; // 对应的物理帧号
} PTE;

// 页目录项 (PDE - Page Directory Entry)
// 包含指向页表的指针和存在位
typedef struct {
    bool present_bit; // 存在位：1表示该页目录项指向一个有效的页表，0表示无效
    PTE* page_table_base; // 指向一个页表（PTE数组）的指针
} PDE;

// 模拟的页目录表（作为我们模拟的 "CR3寄存器" 指向的地址）
PDE page_directory[PAGE_DIR_SIZE];


/**
 * @brief 模拟MMU进行地址翻译和权限检查
 * * @param virtual_address 要翻译的32位虚拟地址
 * @param is_write_access 访问类型，true表示写操作，false表示读操作
 */
void translate_address(uint32_t virtual_address, bool is_write_access) {//请你完成这个尚未完成的函数
    printf("\n----------------------------------------\n");
    printf("Translating Virtual Address: 0x%08X (%s access)\n", virtual_address, is_write_access ? "WRITE" : "READ");

    // --- 步骤1: 从虚拟地址中提取索引和偏移 ---
    uint32_t page_dir_index;
    uint32_t page_table_index;
    uint32_t offset;
    // 利用位运算（移位 >> 和 掩码 &）提取对应部分
    // 请补全代码写在TO DO与END OF TO DO之间：
    // TO DO:
    page_dir_index=(virtual_address>>(PAGE_TABLE_BITS+OFFSET_BITS))&(PAGE_DIR_SIZE-1);
    page_table_index=(virtual_address>>(OFFSET_BITS))&(PAGE_TABLE_SIZE-1);
    offset=virtual_address&(PAGE_SIZE-1);

    // END OF TO DO：

    printf(" -> Page Dir Index: %u (0x%X)\n", page_dir_index, page_dir_index);
    printf(" -> Page Table Index: %u (0x%X)\n", page_table_index, page_table_index);
    printf(" -> Offset: %u (0x%X)\n", offset, offset);

    // --- 步骤2: 查询页目录表 ---
    // 请补全代码写在TO DO与END OF TO DO之间：
    // TO DO:
    printf("  [*] Checking Page Directory Entry %u...\n",page_dir_index);
    if(page_directory[page_dir_index].present_bit==false)
    {
      printf("  [!] FAULT: Page Directory Entry not present. (Segmentation Fault)\n");
      return;
    }
    else
    {
      printf("      -> PDE is present. Page table base address: %p\n", page_directory[page_dir_index].page_table_base);
    }

    // END OF TO DO：

    // --- 步骤3: 查询页表 ---
    // 请补全代码写在TO DO与END OF TO DO之间：
    // TO DO:
     printf("  [*] Checking Page Table Entry %u...\n",page_table_index);
     if(page_directory[page_dir_index].page_table_base[page_table_index].present_bit==false)
     {
      printf("  [!] FAULT: Page Table Entry not present. (Page Fault)");
      return;
     }
     else
     {
      printf("      -> PTE is present. Frame number: %u(0x%X)\n",page_directory[page_dir_index].page_table_base[page_table_index].frame_number,page_directory[page_dir_index].page_table_base[page_table_index].frame_number);
     }

    // END OF TO DO：

    // --- 步骤4: 检查访问权限 ---
    // 请补全代码写在TO DO与END OF TO DO之间：
    // TO DO:
     printf("  [*] Checking access permissions...\n");
     if(is_write_access&&(page_directory[page_dir_index]. page_table_base[page_table_index].rw_bit==false))
     {
     printf("  [!] FAULT: Write attempt on a read-only page. (Protection Fault)\n");
      return;
     }
     else{
      printf("      -> Access granted.\n");
     }

    // END OF TO DO：

    // --- 步骤5: 计算最终的物理地址 ---
    // 请补全代码写在TO DO与END OF TO DO之间：
    // TO DO:
   uint32_t physical_address=(page_directory[page_dir_index]. page_table_base[page_table_index].frame_number<<12)|offset;


    // END OF TO DO：
    printf("  [SUCCESS] Translation complete.\n");
    printf("  Virtual Address 0x%08X  =>  Physical Address 0x%08X\n", virtual_address, physical_address);
}

/**
 * @brief 初始化模拟环境，预设一些页表和页目录项
 */
void initialize_simulation() {
    printf("Initializing MMU simulation environment...\n");

    // 初始化整个页目录表
    for (int i = 0; i < PAGE_DIR_SIZE; ++i) {
        page_directory[i].present_bit = false;
        page_directory[i].page_table_base = NULL;
    }

    // 2. 创建并填充第一个页表 (用于虚拟地址 0x00000000 - 0x003FFFFF)
    //    假设页目录索引为0
    PTE* page_table_1 = (PTE*)malloc(sizeof(PTE) * PAGE_TABLE_SIZE);

    page_directory[0].present_bit = true;
    page_directory[0].page_table_base = page_table_1;

    for (int i = 0; i < PAGE_TABLE_SIZE; ++i) {
        page_table_1[i].present_bit = false; // 默认所有PTE无效
    }
    // 设置几个有效的PTE
    // VA 0x00001xxx -> PA 0x0001Axxx (可读可写)
    page_table_1[1].present_bit = true;
    page_table_1[1].rw_bit = true;
    page_table_1[1].frame_number = 26; // 物理帧号 0x1A

    // VA 0x00002xxx -> PA 0x0008Fxxx (只读)
    page_table_1[2].present_bit = true;
    page_table_1[2].rw_bit = false; // 只读页面
    page_table_1[2].frame_number = 143; // 物理帧号 0x8F

    // 3. 创建并填充第二个页表 (用于虚拟地址 0x00400000 - 0x007FFFFF)
    //    假设页目录索引为1
    PTE* page_table_2 = (PTE*)malloc(sizeof(PTE) * PAGE_TABLE_SIZE);
    page_directory[1].present_bit = true;
    page_directory[1].page_table_base = page_table_2;

    for (int i = 0; i < PAGE_TABLE_SIZE; ++i) {
        page_table_2[i].present_bit = false;
    }
    // VA 0x00400xxx -> PA 0x00033xxx
    page_table_2[0].present_bit = true;
    page_table_2[0].rw_bit = true;
    page_table_2[0].frame_number = 51; // 物理帧号 0x33

    printf("Initialization complete.\n\n");
}

// --- 4. 主函数，运行测试用例 ---

int main() {
    initialize_simulation();

    // --- 测试用例 ---

    // 1. 成功读取: 访问一个有效的、可读写的地址
    // 虚拟地址: 0x00001A2B
    // -> 页目录索引: 0, 页表索引: 1, 偏移: 0xA2B
    // -> 查找 PDE[0] -> PTE[1] -> 物理帧号 26 (0x1A)
    // -> 物理地址: (26 << 12) | 0xA2B = 0x1A000 | 0xA2B = 0x1AA2B
    translate_address(0x00001A2B, false);

    // 2. 成功写入: 访问一个有效的、可读写的地址
    // 与上面相同，但请求是写操作
    translate_address(0x00001A2B, true);

    // 3. 保护错误: 尝试写入一个只读页面
    // 虚拟地址: 0x00002048
    // -> 页目录索引: 0, 页表索引: 2, 偏移: 0x048
    // -> 查找 PDE[0] -> PTE[2] -> rw_bit = 0, 触发保护错误
    translate_address(0x00002048, true);

    // 4. 缺页错误: 访问一个页表项(PTE)无效的地址
    // 虚拟地址: 0x00003555
    // -> 页目录索引: 0, 页表索引: 3, 偏移: 0x555
    // -> 查找 PDE[0] -> PTE[3] -> present_bit = 0, 触发缺页错误
    translate_address(0x00003555, false);

    // 5. 段错误: 访问一个页目录项(PDE)无效的地址
    // 虚拟地址: 0x00804000 (页目录索引=2)
    // -> 页目录索引: 2
    // -> 查找 PDE[2] -> present_bit = 0, 触发段错误
    translate_address(0x00804000, false);

    // --- 释放动态分配的内存 ---
    // 在真实OS中，这部分内存管理会更复杂
    free(page_directory[0].page_table_base);
    free(page_directory[1].page_table_base);

    return 0;
}



/*
sample output:

Initializing MMU simulation environment...
Initialization complete.

----------------------------------------
Translating Virtual Address: 0x00001A2B (READ access)
 -> Page Dir Index: 0 (0x0)
 -> Page Table Index: 1 (0x1)
 -> Offset: 2603 (0xA2B)
  [*] Checking Page Directory Entry 0...
      -> PDE is present. Page table base address: 0x60000305c010
  [*] Checking Page Table Entry 1...
      -> PTE is present. Frame number: 26 (0x1A)
  [*] Checking access permissions...
      -> Access granted.
  [SUCCESS] Translation complete.
  Virtual Address 0x00001A2B  =>  Physical Address 0x0001AA2B
----------------------------------------
Translating Virtual Address: 0x00001A2B (WRITE access)
 -> Page Dir Index: 0 (0x0)
 -> Page Table Index: 1 (0x1)
 -> Offset: 2603 (0xA2B)
  [*] Checking Page Directory Entry 0...
      -> PDE is present. Page table base address: 0x60000305c010
  [*] Checking Page Table Entry 1...
      -> PTE is present. Frame number: 26 (0x1A)
  [*] Checking access permissions...
      -> Access granted.
  [SUCCESS] Translation complete.
  Virtual Address 0x00001A2B  =>  Physical Address 0x0001AA2B
----------------------------------------
Translating Virtual Address: 0x00002048 (WRITE access)
 -> Page Dir Index: 0 (0x0)
 -> Page Table Index: 2 (0x2)
 -> Offset: 72 (0x48)
  [*] Checking Page Directory Entry 0...
      -> PDE is present. Page table base address: 0x60000305c010
  [*] Checking Page Table Entry 2...
      -> PTE is present. Frame number: 143 (0x8F)
  [*] Checking access permissions...
  [!] FAULT: Write attempt on a read-only page. (Protection Fault)
----------------------------------------
Translating Virtual Address: 0x00003555 (READ access)
 -> Page Dir Index: 0 (0x0)
 -> Page Table Index: 3 (0x3)
 -> Offset: 1365 (0x555)
  [*] Checking Page Directory Entry 0...
      -> PDE is present. Page table base address: 0x60000305c010
  [*] Checking Page Table Entry 3...
  [!] FAULT: Page Table Entry not present. (Page Fault)
----------------------------------------
Translating Virtual Address: 0x00804000 (READ access)
 -> Page Dir Index: 2 (0x2)
 -> Page Table Index: 4 (0x4)
 -> Offset: 0 (0x0)
  [*] Checking Page Directory Entry 2...
  [!] FAULT: Page Directory Entry not present. (Segmentation Fault)
*/
```
### 2.3
1. 与内存组织相关的寄存器有什么？他们分别有什么作用？
* 与内存组织和管理相关的寄存器，主要分为CPU内部寄存器和内存硬件寄存器两大类。CPU内部寄存器是CPU或MMU的一部分，负责虚拟地址到物理地址的转换，以及内存保护。如CR3,存放当前进程的一级页表（页目录）的物理基地址;CR0（控制寄存器 0）,用于开启或关闭分页机制;CR2（页错误地址寄存器）,用来记录缺页地址；CR4，运行32位系统支持超过4GB的物理内存。段寄存器和基址寄存器辅助寻址计算。内存硬件端（存储芯片内部寄存器），位于内存条或内存控制器上，包括行地址选通寄存器（RAS）与 列地址选通寄存器（CAS），用于定位物理内存上一个一个具体的储存单元，还有内存控制器的配置寄存器（如 MTRR），用来控制内存的缓冲策略。
2. 一次从内存中完整读取数据的过程是怎么样的？一次从存储中完整读取数据的过程是什么样的？
![alt text](fa2ea178fe9cefe3ccef22fd9336f214.jpg)
3. 什么是缺页异常 ？它分为哪些种类？当发生不同缺页异常时，操作系统分别会怎么处理？
* 缺页异常是CPU访问内存时，发现目标虚拟页没有映射到物理内存，从而引发中断。
* 分为软缺页，硬缺页和非法访问。软缺页是页已经在物理内存里了，只是当前进程的页表还没建立映射，常见于共享库。硬缺页是页根本不在物理内存里，必须去硬盘（或SWAP空间）读进来。非法访问是访问的虚拟地址根本就不合法。
* 面对这三种情况，CPU首先会保存现场，将页的虚拟地址存入 CR2 寄存器，把出错指令的地址压栈。随后CPU切换内核态，执行执行操作系统的缺页异常处理程序。第三步操作系统读取CR2，知道是哪个虚拟地址出事了。第四步查进程的 VMA（虚拟内存区域）表，看这个地址合不合法。接下来分三种情况：1.软缺页的话直接在页表上填上物理页框号，更行TLB返回切换成用户态执行程序。2.硬缺页的话首先在物理内存中找一个空闲页框，然后发起磁盘I/O，把数据从硬盘读到内存，此时当前进程被挂起（阻塞），OS调度其他进程去跑。当盘读完数据发出中断，OS 把页表填好，最后唤起进程，返回用户态。3.如果是非法访问的化操作系统会直接向进程发送段错误了信号，既不访问磁盘，也不访问内存程序中断。
4. 什么是页面替换？它是怎么样进行的？怎么找到适合替换的页？
* 页面替换是在物理内存满了的时候，操作系统挑出一个现有的内存页，把它赶出去（写到硬盘的 Swap 区），腾出位置给新的页用的过程。
* ![alt text](e481d6abdfd18c56af4fd5fa49183163.jpg)
* 根据页面替换算法（局部性原理来猜测），常见的有最佳替换算法，替换未来最长时间内不会被访问的页；先进先出算法，替换最早进入内存的页；最近最久未使用算法，基于时间局限性，替换过去最长时间没有被访问的页；时钟算法，把内存页排成一个环，每个页有一个访问位，指针像时钟一样扫过这些页，指针指向的访问位是1（最近用过），替换为0，指针后移。如果访问位是0（最近没用），直接选中它替换。
5. 64位操作系统和32位操作系统的不同

|不同之处|32位|64位|
|:---:|:---:|:---:|
|虚拟地址空间大小|2的32次方4GB|2的64次方16EB|
|几级页表|2到3级|4到5级|
|单级页表大小|4MB|不存在|
|虚拟地址划分|10位页目录号，10位页表号，12位页内偏移|48位寻址，索引的36位，加上12位偏移量|
|页表项大小|4字节|8字节|
|TLB|压力较小，全部刷新|压力大，刷新保留部分|
|大页|支持，用的少|支持得多|
# step3
### 3.1
1. 栈在内存地址的增长方向上有什么特殊之处？
* 栈是自上向下，从高地址往低地址方向走。
2. 栈帧是什么？有什么作用？
* 栈帧，也叫活动记录，是函数调用时在栈上分配的一块内存区域，每次调用一次函数，给它分配的一片临时工作台，执行完就收回。存有函数参数，返回地址，保存的旧基址指针（指向上一层函数（调用者）的栈底，用于回溯），局部变量和临时数据等。
* 作用：隔离变量（不同函数中的相同变量也是不同的）、保存返回地址、支持递归、传递参数。同一个函数递归过程中会创建不同的栈帧，不同栈帧的变量完全不同互补干扰，这就解释了为什么递归的每层函数变量都是不同的。
3. 当发生函数调用时，CPU 的核心寄存器 EBP/RBP（基址指针） 和 ESP/RSP（栈顶指针） 分别起到了什么作用？
* 两者相互配合，ESP负责固动态移动，EBP负责固定锚点。ESP永远指向当前栈的最顶端（当前最后压入的数据），是动态变化的，压栈指针向低地址移动，出栈向高地址移动。EBP是基址指针，固定栈顶的锚点，在一个函数执行期间，EBP 的值固定不变，作为当前函数栈帧的“基准坐标”，便于精准定位找到函数的各种参数变量等。
4. 在函数调用的那一瞬间，程序是如何记住“执行完这个函数后，该回到哪里继续执行”的？这个信息（Return Address返回地址）在栈帧中具体存放在什么位置？
* 返回地址是CALL指令自动压入栈的。当代码执行到CALL函数时，它会计算返回地址，将这样一个返回地址压入栈顶，然后跳转执行当前函数，这样函数就知道该返回哪里继续执行了。
* 位置：在栈帧中，位于 [EBP + 4]（32 位系统），即栈帧最底部（靠近调用者函数栈帧那一侧），被调用函数栈帧的第一个元素。函数把返回地址压栈，大小为4个字节，然后将EBP压栈，这样EBP的上方4个位置就是返回地址。
### 3.2
1. 请指出程序中 gets(password); 这行代码为什么极其危险？这种漏洞在网络安全中统称为什么？
* 使用gets读取用户输入，但gets()根本不知道数组有多大，会无限制地往内存里写。一旦输入超长，就会覆盖掉栈上的其他数据，甚至改变程序的执行流。从低地址往高地址，如果太长（超过16字节）它会覆盖掉EBP和返回地址。甚至有人会专门这样做，覆盖掉返回地址，让它指向隐藏的grant_access函数。这种漏洞叫栈溢出漏洞或广泛称为缓冲区溢出。
2. 16字节任意字符串（覆盖掉password）+4字节任意字符串（覆盖掉旧的EBS）+grant_access的地址，在这里地址要用小端序，低地址存放地位，高地址存放高位，即写为\x56\x11\x40\x00，这是因为出栈过程时从低地址向高地址读的，这样读出来的才是0x401156，负责读出来的就是相反的。
### 3.3
了解了地址空间布局随机化，在思考如何实现其的随机化上使用了AI。

![alt text](QQ20261017-171231.png)