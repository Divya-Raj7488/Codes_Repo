import fs from 'fs/promises';
import path from 'path';
const finalData = (props) => {
    // dataFromApi name of is data extracted from api.
    
    const {dataFromApi} = props;
return(
    <div key={dataFromApi.id}>{dataFromApi.property}</div>
);
}


export async function getStaticProps(){
    const filePath = path.join(/*path of json file containing data frpm Api*/);
    const jsonData = await fs.readFile(filePath);
    const data = JSON.parse(jsonData);
    return {props: {
     dataFromApi:data.dataFromApi
    } }
}
export default finalData;