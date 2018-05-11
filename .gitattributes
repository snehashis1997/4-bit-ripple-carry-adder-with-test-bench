module csaadder(a,b,carryin,cout,sum);

  input carryin;
  input [3:0] a,b;
  wire [3:1] c;
  output cout;
  output [3:0] sum;

  fa s1(c[1],sum[0],carryin,a[0],b[0]);
  fa s2(c[2],sum[1],c[1],a[1],b[1]);
  fa s3(c[3],sum[2],c[2],a[2],b[2]);
  fa s4(carryout,sum[3],c[3],a[3],b[3]);
endmodule

module fa(cout,su,a,b,c);
 input a,b,c;
 output cout,su;
 assign su=a^b^c;
 assign cout=(a&b)|(b&c)|(c&a);
endmodule

//test bench
module testbench;
 reg [3:0] a,b;
 reg c;
 wire [3:0] s;
 wire cout;
 csaadder fa(a,b,c,cout,s);
 initial
  begin
   $dumpfile ("csaadder.vcd");
   $dumpvars(0,testbench);
  // $monitor($time ," a=%b, b=%b, c=%b, sum=%b, cout=%b",a,b,c,s,cout);
   #5 a=0001; b=0010 ; c=1;
   #5 a=0001; b=0000 ; c=0;
   #5 a=0001; b=0010 ; c=1;
  end
endmodule


