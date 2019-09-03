# test-archives
These data are Public Domain.

Test archives containing 2099 files. File names contain Japanese characters.

These archives are used to test LhaForge.

日本語ファイル名を含むアーカイブ。LhaForgeのテスト用に使用していました。

# Major formats
- test_2099.zip
- test_2099.lzh
- test_2099.rar
- test_2099.tar
- test_2099.tbz: tar+bz2
- test_2099.tgz: tar+gzip
- test_2099.cab

#Minor formats
- test.bel: Belon format. See https://www.vector.co.jp/soft/win95/util/se079561.html
- test_2099.GCA: GCA format. See http://www.emit.jp/
- test_2099.ace: Ace format. See http://www.madobe.net/archiver/lib/UnAceV2J.html
- test_2099.arj: Arj format. See https://micco.mars.jp/mysoft/unarj32.htm
- test_2099.bh: BlakHole format. Gone history.
- test_2099.bza / test_2099.gza: Archive format of Bga32.dll. See http://www.csdinc.co.jp/archiver/lib/bga32.html . 
- test_2099.hki: HKI format. See https://www.winhki.com/
- test_2099.imp: IMP format. See http://technelysium.com.au/wp/imp-file-archiver/

## YZ1 format
- test_2099.pass.yz1: YZ1 format with password. Password is "pass"
- test_2099.pub_pass.yz1: YZ1 format with public key cryptosystem. Public key is "pub-206e-a3c4-b5"
- test_2099.yz1: YZ1 format, no password


##Note:
For bza/gza, header format information is found in BgaTool.h, from http://www.kmonos.net/lib/xacrett.ja.html
~~~
struct BgaHeader
{
	DWORD checksum;			// signed で type-fname の和
	char  type[4];			// "GZIP" または "BZ2"
	DWORD compressed_size;	// 圧縮後のデータサイズ( ヘッダは含まない )
	DWORD original_size;	// 元のファイルサイズ
	WORD  date;				// ファイルの更新日付( DOS形式 )
	WORD  time;				// ファイルの更新時刻( DOS形式 )
	BYTE  attrib;			// ファイルの属性
							// ( 1:RO 2:Hid 4:Sys 8:Vol 16:Dir 32:Arc )
	BYTE  header_type;		// ヘッダの種類( 現在は常に 0 )
	WORD  arc_type;			// アーカイブタイプ
							// 0:(ext==↓ ? 非圧縮 : 圧縮) 1:圧縮 2:非圧縮
							//	.ARC, .ARJ, .BZ2, .BZA, .CAB, .GZ, .GZA, .LZH,
							//	.LZS, .PAK, .RAR, .TAZ, .TBZ, .TGZ, .Z, .ZIP, .ZOO
	WORD  dir_name_len;		//
	WORD  file_name_len;	//
	char  name[MAX_PATH];	// dir_name_len + file_name_len ( no '\0' )
};
~~~
