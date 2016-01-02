---
layout: post
category : lessons
tags : [bigData, tutorial]
---

NOSQL since 2010 has been developed for four years. One of the most fire Mongodb also been known, but he has been no opportunity to learn under this aspect, little time recently looked under Mongodb of bson agreement, under the guidance of my colleagues, sorted out for everyone to share. As for the concept of BSON I will not go into details, through google to query it.

<!--break-->

{% include JB/setup %}

The following is written in java BSON binary data generated pseudo-code:


        map = new map ();
        map.put ("data", "{id: '1', name: 'Joe Smith'}");
        BSONObject bson = parse (map);
        byte [] bsonBytes = bson.toByte ();
        //Generate results:
    
        bsonBytes = {52, 0, 0, 0, 5, 100, 97, 116, 97, 0, 36, 0, 0, 0, 0,123,
        0, 105, 0, 100, 0, 58, 0, 39, 0, 49, 0, 39, 0, 44, 0, 110,0, 97, 0, 109,
        0, 101, 0,58, 0, 39, 0, 32, 95, 9, 78, 39, 0,125, 0, 0};

            //For convenience of explanation later, the first bsonBytes simple format
             bsonBytes = {
                 52, 0, 0, 0,
                 5,
                 100, 97, 116, 97,
                 0
                 36, 0, 0, 0,
                 0
                
                 123, 0, 105, 0, 100, 0, 58, 0, 39, 0, 49, 0, 39, 0, 44, 0, 110,0, 97,
                 0, 109, 0, 101, 0,58, 0, 39, 0, 32, 95, 9, 78, 39, 0,125, 0,
                 0
             };


    //Open BSON Protocol page: http: //bsonspec.org/spec.html, according to the page will bsonBytes to generate binary comment.
    
    bsonBytes = {
    52, 0, 0, 0,  【 int32 is the total number of bytes comprising the document 】
    5,                   【"\x05" e_name binary Binary data】
    100, 97, 116, 97, 【:e_name:cstring byte*) "\x00"】
    0,                             【:e_name:cstring byte*) "\x00"】
    36, 0, 0, 0, 【int32 subtype (byte*)】
    0,                【int32 subtype (byte*) subtype ::= "\x00" Generic binary subtype】
    123, 0, 105, 0, 100, 0, 58, 0, 39, 0, 49, 0, 39, 0, 44, 0, 110,0, 97, 0, 109, 0, 101, 0,58, 0, 39, 0, 32, 95, 9, 78, 39, 0,125, 0,           【消息主体的二进制数据】(字符串形式为：{id:'1',name:'张三'})
    0                 【document ::= int32 e_list "\x00"】
    
    };

over! ! ! o (∩∩) o ...