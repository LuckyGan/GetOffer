设计思想：无须设计新的硬件，只对现有硬件(网络设备中内置的 TCAM 存储器)更新其软件。

传统网络设备的控制平面和数据平面位于同一设备中，这是因为各个网络设备采用自律分散协助的模式
比如：路由器利用路由协议计算出各自合适的路由，并依据计算结果发送数据包，路由器就同时包含计算路由的控制平面和转发数据包的数据平面。

OpenFlow 控制器和 OpenFlow 交换机始终维持着经由 OpenFlow 通道的 TCP 连接，该 OpenFlow 通道是从 OpenFlow 交换机向 OpenFlow 控制器建立的。

Proactive 模式：在 OpenFlow 控制器和 OpenFlow 交换机之间建立 OpenFlow 通道后，由 OpenFlow 控制器向 OpenFlow 交换机预先发送流表项的设置。
Reactive 模式：当 OpenFlow 交换机接收到未知数据包时，向 OpenFlow 控制询问如何处理。

在 OpenFlow 1.3 实现标准化后，经 ONF 一致同意，将 OpenFlow 1.3 更新成为具有互通性的版本。

建立 OpenFlow 通道的 TCP 端口号默认使用6653号。

Modify Flow Entry Message 消息(Flow-Mod 消息)是由 OpenFlow 控制器对 OpenFlow 交换机设置流表项的消息。

idle_time：软时间，如果与流表项匹配的数据包超过该时间还未到达则删除流表项
hard_time：硬时间，流表项添加的时间超过该时间则删除流表项


使用 Packet-In 消息的目的是为了将到达 OpenFlow 交换机的数据包发送至 OpenFlow 控制器。
Packet-Out 消息是从 OpenFlow 控制器向 OpenFlow 交换机发送的消息，是包含数据包发送命令的消息。

LLDP 是数据链路层的协议，用于对数据链路层的连接进行检测、管理。OpenFlow 控制器利用 LLDP 来检测网络拓扑结构。