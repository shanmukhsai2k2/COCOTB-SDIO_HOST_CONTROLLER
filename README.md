# COCOTB-SDIO_PROTOCOL
# SDIO Regiter Information

The following table provides the register definitions for the hardware module. Each register is identified by a symbolic name along with its corresponding 5-bit address.

## Receiver Registers

- **Base Address:** `BASEADDR`

| Symbolic Name  | Address Offset | Description                    |
| -------------- | -------------- | ------------------------------ |
| `REG_RX_SADDR` | 0x00           | Receiver Start Address         |
| `REG_RX_SIZE`  | 0x04           | Receiver Size                  |
| `REG_RX_CFG`   | 0x08           | Receiver Configuration         |
| `REG_RX_INTCFG`| 0x0C           | Receiver Interrupt Configuration|

## Transmitter Registers

- **Base Address:** `BASEADDR`

| Symbolic Name  | Address Offset | Description                    |
| -------------- | -------------- | ------------------------------ |
| `REG_TX_SADDR` | 0x10           | Transmitter Start Address      |
| `REG_TX_SIZE`  | 0x14           | Transmitter Size               |
| `REG_TX_CFG`   | 0x18           | Transmitter Configuration      |
| `REG_TX_INTCFG`| 0x1C           | Transmitter Interrupt Configuration|

## Command Registers

- **Base Address:** `BASEADDR`

| Symbolic Name  | Address Offset | Description                    |
| -------------- | -------------- | ------------------------------ |
| `REG_CMD_OP`   | 0x20           | Command Operation              |
| `REG_CMD_ARG`  | 0x24           | Command Argument               |
| `REG_DATA_SETUP`| 0x28          | Data Setup                     |
| `REG_START`    | 0x2C           | Start Command                  |

## Response Registers

- **Base Address:** `BASEADDR`

| Symbolic Name  | Address Offset | Description                    |
| -------------- | -------------- | ------------------------------ |
| `REG_RSP0`     | 0x30           | Response 0                     |
| `REG_RSP1`     | 0x34           | Response 1                     |
| `REG_RSP2`     | 0x38           | Response 2                     |
| `REG_RSP3`     | 0x3C           | Response 3                     |

## Configuration Registers

- **Base Address:** `BASEADDR`

| Symbolic Name  | Address Offset | Description                    |
| -------------- | -------------- | ------------------------------ |
| `REG_CLK_DIV`  | 0x40           | Clock Divider                  |
| `REG_STATUS`   | 0x44           | Status                         |

## Stop Command Configuration Registers

- **Base Address:** `BASEADDR`

| Symbolic Name     | Address Offset | Description                      |
| ----------------- | -------------- | -------------------------------- |
| `REG_STOPCMD_OP`  | 0x48           | Stop Command Operation           |
| `REG_STOPCMD_ARG` | 0x52           | Stop Command Argument            |

Please make sure to replace `BASEADDR` with the actual base address value used in your hardware module.


# Signal Information

Below is a description of the signals used in the hardware module:

## Clock and Reset Signals

- `clk_i`: Clock input.
- `rstn_i`: Active-low asynchronous reset input.

## Status Control Signal

- `clr_stat_i`: Signal to clear status.

## Command Interface Signals

- `cmd_start_i`: Start command signal.
- `cmd_op_i`: Command operation code (6 bits).
- `cmd_arg_i`: Command argument (32 bits).
- `cmd_rsp_type_i`: Command response type (3 bits).

## Stop Command Interface Signals

- `stopcmd_op_i`: Stop command operation code (6 bits).
- `stopcmd_arg_i`: Stop command argument (32 bits).
- `stopcmd_rsp_type_i`: Stop command response type (3 bits).

## Response Data Signal

- `rsp_data_o`: Output response data (128 bits).

## Data Interface Signals

- `data_en_i`: Data enable signal.
- `data_rwn_i`: Data read/write control signal.
- `data_quad_i`: Data quad enable signal.
- `data_block_size_i`: Data block size (10 bits).
- `data_block_num_i`: Data block number (8 bits).

## End-of-Transmission Signal

- `eot_o`: End-of-transmission signal.

## Status Output Signal

- `status_o`: Output status (16 bits).

## Input Data Interface Signals

- `in_data_if_data_i`: Input data interface data (32 bits).
- `in_data_if_valid_i`: Input data interface valid signal.
- `in_data_if_ready_o`: Output signal indicating readiness to accept input data.

## Output Data Interface Signals

- `out_data_if_data_o`: Output data interface data (32 bits).
- `out_data_if_valid_o`: Output data interface valid signal.
- `out_data_if_ready_i`: Input signal indicating readiness to accept output data.

## SD Card Interface Signals

- `sdclk_o`: Output signal for SD card clock.
- `sdcmd_i`: Input signal for SD card command.
- `sdcmd_o`: Output signal for SD card command.
- `sdcmd_oen_o`: Output enable for SD card command.
- `sddata_o`: Output signal for SD card data (4 bits).
- `sddata_i`: Input signal for SD card data (4 bits).
- `sddata_oen_o`: Output enable for SD card data.

These signals collectively define the interface and control for the hardware module, possibly interacting with an SD card and managing various commands and data. Specific functionalities and interactions can be further detailed in the design documentation.
