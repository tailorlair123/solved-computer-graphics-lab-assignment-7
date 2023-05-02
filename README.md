Download Link: https://assignmentchef.com/product/solved-computer-graphics-lab-assignment-7
<br>
<strong>Computer Graphics, Lab Assignment 7 </strong>




<ol>

 <li>Start from the following code skeleton.</li>

</ol>

<table width="548">

 <tbody>

  <tr>

   <td width="548"><strong>import</strong> glfw<strong>from</strong> OpenGL<strong>.</strong>GL <strong>import</strong> <strong>*</strong> <strong>import</strong> numpy <strong>as</strong> np <strong>from</strong> OpenGL<strong>.</strong>GLU <strong>import</strong> <strong>*</strong><strong>def</strong> render<strong>():</strong>glClear<strong>(</strong>GL_COLOR_BUFFER_BIT <strong>|</strong> GL_DEPTH_BUFFER_BIT<strong>)</strong>     glEnable<strong>(</strong>GL_DEPTH_TEST<strong>)</strong> glMatrixMode<strong>(</strong>GL_PROJECTION<strong>)</strong>     glLoadIdentity<strong>()</strong>     glOrtho<strong>(-</strong>2<strong>,</strong>2<strong>,</strong> <strong>–</strong>2<strong>,</strong>2<strong>,</strong> <strong>–</strong>1<strong>,</strong>1<strong>)</strong> glMatrixMode<strong>(</strong>GL_MODELVIEW<strong>)</strong>     glLoadIdentity<strong>()</strong> drawFrame<strong>()</strong>t <strong>=</strong> glfw<strong>.</strong>get_time<strong>()</strong> # blue base transformation     glPushMatrix<strong>()</strong>     glTranslatef<strong>(</strong>np<strong>.</strong>sin<strong>(</strong>t<strong>),</strong> 0<strong>,</strong> 0<strong>)</strong> # blue base drawing     glPushMatrix<strong>()</strong>     glScalef<strong>(</strong>.2<strong>,</strong> .2<strong>,</strong> .2<strong>)</strong>     glColor3ub<strong>(</strong>0<strong>,</strong> 0<strong>,</strong> 255<strong>)</strong>     drawBox<strong>()</strong>     glPopMatrix<strong>()</strong> # red arm transformation     glPushMatrix<strong>()</strong> glRotatef<strong>(</strong>t<strong>*(</strong>180<strong>/</strong>np<strong>.</strong>pi<strong>),</strong> 0<strong>,</strong> 0<strong>,</strong> 1<strong>)</strong>glTranslatef<strong>(</strong>.5<strong>,</strong> 0<strong>,</strong> .01<strong>)</strong> # red arm drawing     glPushMatrix<strong>()</strong>     glScalef<strong>(</strong>.5<strong>,</strong> .1<strong>,</strong> .1<strong>)</strong>     glColor3ub<strong>(</strong>255<strong>,</strong> 0<strong>,</strong> 0<strong>)</strong>     drawBox<strong>()</strong>     glPopMatrix<strong>()</strong></td>

  </tr>

  <tr>

   <td width="548">     glPopMatrix<strong>()</strong>     glPopMatrix<strong>()</strong><strong>def</strong> drawBox<strong>():</strong>glBegin<strong>(</strong>GL_QUADS<strong>)</strong>     glVertex3fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>1<strong>,</strong>1<strong>,</strong>0.<strong>]))</strong>     glVertex3fv<strong>(</strong>np<strong>.</strong>array<strong>([-</strong>1<strong>,</strong>1<strong>,</strong>0.<strong>]))</strong>     glVertex3fv<strong>(</strong>np<strong>.</strong>array<strong>([-</strong>1<strong>,-</strong>1<strong>,</strong>0.<strong>]))</strong>     glVertex3fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>1<strong>,-</strong>1<strong>,</strong>0.<strong>]))</strong>     glEnd<strong>()</strong><strong>def</strong> drawFrame<strong>():</strong># draw coordinate: x in red, y in green, z in blue     glBegin<strong>(</strong>GL_LINES<strong>)</strong>     glColor3ub<strong>(</strong>255<strong>,</strong> 0<strong>,</strong> 0<strong>)</strong>     glVertex3fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>0.<strong>,</strong>0.<strong>,</strong>0.<strong>]))</strong>     glVertex3fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>1.<strong>,</strong>0.<strong>,</strong>0.<strong>]))</strong>     glColor3ub<strong>(</strong>0<strong>,</strong> 255<strong>,</strong> 0<strong>)</strong>     glVertex3fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>0.<strong>,</strong>0.<strong>,</strong>0.<strong>]))</strong>     glVertex3fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>0.<strong>,</strong>1.<strong>,</strong>0.<strong>]))</strong>     glColor3ub<strong>(</strong>0<strong>,</strong> 0<strong>,</strong> 255<strong>)</strong>     glVertex3fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>0.<strong>,</strong>0.<strong>,</strong>0<strong>]))</strong>     glVertex3fv<strong>(</strong>np<strong>.</strong>array<strong>([</strong>0.<strong>,</strong>0.<strong>,</strong>1.<strong>]))</strong>     glEnd<strong>()</strong><strong>def</strong> main<strong>():</strong>     <strong>if</strong> <strong>not</strong> glfw<strong>.</strong>init<strong>():</strong><strong>return</strong>     window <strong>=</strong> glfw<strong>.</strong>create_window<strong>(</strong>480<strong>,</strong>480<strong>,</strong>‘2017123456-lab6-1’<strong>,</strong> <strong>None</strong><strong>,</strong><strong>None</strong><strong>)</strong>     <strong>if</strong> <strong>not</strong> window<strong>:</strong>         glfw<strong>.</strong>terminate<strong>()</strong>         <strong>return</strong>glfw<strong>.</strong>make_context_current<strong>(</strong>window<strong>)</strong>     glfw<strong>.</strong>swap_interval<strong>(</strong>1<strong>)</strong><strong>while</strong> <strong>not</strong> glfw<strong>.</strong>window_should_close<strong>(</strong>window<strong>):</strong>         glfw<strong>.</strong>poll_events<strong>()</strong>         render<strong>()</strong>glfw<strong>.</strong>swap_buffers<strong>(</strong>window<strong>)</strong> glfw<strong>.</strong>terminate<strong>()</strong><strong>if</strong> __name__ <strong>==</strong> “__main__”<strong>:</strong>main<strong>()</strong></td>

  </tr>

 </tbody>

</table>

<ol>

 <li><strong>Add a green arm at the end of the red arm, and rotate the green arm about its local </strong></li>

</ol>

<strong>z axis. </strong>

<ol>

 <li>Render the green arm using drawBox().</li>

 <li><strong>Also render local frames of the blue base, red arm, green arm using drawFrame(). </strong></li>

 <li>Expected result: Uploaded LabAssignment7-1.mp4</li>

 <li>Submit a single .py file – <strong>[studentID]-[assignment#]-[prob#].py</strong></li>

</ol>










<ol start="2">

 <li>Write down a Python program to draw following triangular pyramid (삼각뿔) by <strong>using indexed triangles representation and glDrawElements()</strong>.</li>

 <li></li>

 <li>Start from the code in 7-Hierarchy,Mesh slides. Make sure camera manipulation shortcuts</li>

</ol>

‘1’, ‘3’, ‘2’, ‘w’ work.

<ol>

 <li>Set the window title to <strong>[studentID]-[assignment#]-[prob#] </strong>and the window size to (480,480).</li>

 <li>Submit a single .py file – <strong>[studentID]-[assignment#]-[prob#].py</strong></li>

</ol>