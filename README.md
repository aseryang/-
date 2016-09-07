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
