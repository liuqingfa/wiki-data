# API

## Trid_Demux_Init
- **Protocol**
RETURN_TYPE Trid_Demux_Init (trid_sint32 deviceid);
- **Description**
initialize demux
- **Parameters**
@param[in]      deviceid the index of device, now just support one device, so set it to 0
- **Return**
SYS_NOERROR:OK, 
OTHER:ERROR Code

## Trid_Demux_Exit
- **Protocol**
RETURN_TYPE Trid_Demux_Exit (trid_sint32 deviceid);
- **Description**
exit demux filter manager
- **Parameters**
@param[in]      deviceid see Trid_Demux_Init
- **Return**
SYS_NOERROR:OK, 
OTHER:ERROR Code

## Trid_Demux_MainInputEnable
- **Protocol**
RETURN_TYPE Trid_Demux_MainInputEnable(trid_sint32 deviceid, TSSOURCE tsinput, INPUTSOURCE input);
- **Description**
set the demux main channel, input source from SRC01/SRC02/SRC03 or SRC04(Memory) 
- **Parameters**
	@param[in] 		deviceid see Trid_Demux_Init
	@param[in] 		tsinput TS1 or TS2 
	@param[in] 		input input source, PARALLELTS,SERIALTS,
- **Return**
SYS_NOERROR:OK, 
OTHER:ERROR Code

##Trid_Demux_StartDataFilter_ext
- **Protocol**
RETURN_TYPE Trid_Demux_StartDataFilter_ext(trid_sint32 deviceid,
trid_sint32 *pfilterid,
DMXFILTER *pfilter,
Data_Callback notify_callback);
- **Description**
This function is used to start data filter with a registered callback function. The filter parameters is included in the structure DMXFILTER.  
- **Parameters**
@param[in] 		deviceid see Trid_Demux_Init
@param[in] 		pfilterid filter id.
@param[in] 		pfilter set data filter parameters
@param[in] 		notify_callback callback function for the demux data filter.
- **Return**		
SYS_NOERROR:OK, 
OTHER:ERROR Code

##Trid_Demux_StopDataFilter
- **Protocol**
RETURN_TYPE Trid_Demux_StopDataFilter(trid_sint32 deviceid, 
trid_sint32 filterid, trid_bool bFlush);
**Description**
This function is used to stop Demux data filter with specified filterid.
- **Parameters**
@param[in] 		deviceid see Trid_Demux_Init
@param[in] 		filterid filter id.
@param[in] 		bFlush flag to flush data filter buffer
- **Return**	
SYS_NOERROR:OK, 
OTHER:ERROR Code

##Trid_Demux_GetHWSTC
- **Protocol**
RETURN_TYPE Trid_Demux_GetHWSTC(unsigned long long *pHWSTC)
- **Description**
Get STC value
- **Parameters**
@param[in]      pHWSTC		return the STC valuea
- **Return**			
SYS_NOERROR:OK, 
OTHER:ERROR Code

