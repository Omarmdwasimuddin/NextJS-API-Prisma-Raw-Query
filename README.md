## NextJS API---> Prisma raw query

### Prisma Raw SQL Query ($queryRaw)
![](https://imgur.com/j2w8ANM.png)

```bash
import prisma from "@/lib/prisma";
import { NextRequest, NextResponse } from "next/server";


export async function GET(request: NextRequest) {
    try {

        
        const readData = await prisma.$queryRaw`SELECT * FROM "User"`;
        

        return NextResponse.json(
            {status: "success", message: "Read data successfully", data: readData},
            {status: 200}
        )
    } catch (error) {
        return NextResponse.json(
            {status: "failed", message: "Internal server problem"},
            {status: 500}
        )
    }
}
```
---
