【16进制转为字符串】
如 char buf[3] = {0x01, 0x02, 0x03} 转为 010203

void Hex2Str( char *sSrc, char *sDest, int nSrcLen )
{
	int i;
	char szTmp[3];

	for( i = 0; i < nSrcLen; i++ )
	{
		sprintf( szTmp, "%02X", (unsigned char) sSrc[i] );
		memcpy( &sDest[i * 2], szTmp, 2 );
	}
	return ;
}


void Hex2Str(unsigned char *sSrc, unsigned char *sDest, int nSrcLen ) 
{ 
	int i; 
	char szTmp[4];
	for( i = 0; i < nSrcLen; i++ )
	{
		sprintf(szTmp, "%02X ", (unsigned char) sSrc[i] );
		memcpy( sDest + i * 3, szTmp, 3 );
	}
	return ;
}


int _tmain(int argc, _TCHAR* argv[])
{
	//2E 60 05 05 15 FF 64 00 1D
	unsigned char msg[7]={0x10, 0x05, 0x05,0x15,0xff,0x64,0x00};
	unsigned char dst[100] = {0};
	Hex2Str(msg, dst, 7);
	printf("REC: %s \n", dst);
	
	return 0;
}

【log4cpp使用】
http://blog.csdn.net/kingskyleader/article/details/7320826

【协议栈开发心得】
http://blog.csdn.net/findaway123/article/details/18097273
